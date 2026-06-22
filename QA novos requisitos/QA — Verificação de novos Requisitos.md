# Relatório de QA — Verificação de Requisitos

**Projeto:** Sistema de Turismo — Backoffice  
**Escopo:** RF-044 ao RF-057 (exceto RF-053, RF-054, RF-055)  
**Status:** Revisão Inicial  
**Formato:** QA de Requisitos (.md)


---

## Legenda de Prioridade

|Símbolo|Prioridade|Descrição|
|---|---|---|
|🔴|Alta|Impacto direto em regras de negócio, LGPD ou segurança|
|🟡|Média|Ambiguidade que pode gerar implementação incorreta|
|🟢|Baixa|Padronização, nomenclatura, CAs ausentes|

---

## Legenda de Tipo de Achado

|Tipo|Descrição|
|---|---|
|`[CONFLITO]`|Duas regras se contradizem diretamente|
|`[LACUNA]`|Cenário existente não coberto pelo documento|
|`[AMBIGUIDADE]`|Requisito com mais de uma interpretação possível|
|`[NOVO REQUISITO]`|Funcionalidade necessária não prevista|
|`[NOMENCLATURA]`|Inconsistência de nome entre documentos|
|`[SEGURANÇA/LGPD]`|Risco legal ou de segurança identificado|

---

## RF-044 — Gestão de Agências

### QA-044-01 🔴 `[CONFLITO]` Status "Ativa" vs bloqueio por contrato

**Onde:** RF-044.26 + RN-044.15  
**Problema:** RF-044.26 altera o status para "Ativa" na aprovação. RN-044.15 impede a operação enquanto o contrato DocuSign não estiver ativo. O sistema registra a agência como "Ativa" mas ela não pode operar — contradição de estado.

**Resolução:**

- Criar status intermediário **"Aprovada — Aguardando Contrato"**
- A agência só migra para "Ativa" quando o webhook do DocuSign confirmar todas as assinaturas (RF-008)
- Atualizar RF-044.26, RF-044.27 e RF-044.28 para refletir o novo status
- Adicionar RN-044.17: _"O status 'Aprovada — Aguardando Contrato' concede acesso ao Backoffice para fins de configuração, mas bloqueia qualquer operação comercial (venda de ingressos) até o Contrato de Agência atingir status 'Ativo' em RF-008."_

---

### QA-044-02 🔴 `[LACUNA]` RF-044.28 não menciona geração automática de contrato

**Onde:** RF-044.28  
**Problema:** A mensagem de sucesso da aprovação não informa ao Admin que um rascunho de contrato foi gerado em RF-008, apesar de RN-044.14 prever isso.

**Resolução:**

- Atualizar RF-044.28: _"O sistema deve exibir mensagem de sucesso informando quantas agências foram aprovadas e que o(s) rascunho(s) de Contrato de Agência foram gerados em RF-008 para revisão."_

---

### QA-044-03 🔴 `[CONFLITO]` Rejeição → "Inativa" permite reativação sem nova aprovação

**Onde:** RF-044.31 + RN-044.08  
**Problema:** Agência rejeitada recebe status "Inativa". RN-044.08 permite reativar qualquer inativa diretamente para "Ativa" sem nova aprovação — isso incluiria agências que nunca foram aprovadas.

**Resolução:**

- Criar subestado interno: `inativa_por_rejeicao` vs `inativa_por_inativacao`
- Adicionar RN-044.18: _"Agências com histórico de rejeição (nunca aprovadas) ao serem reativadas devem retornar ao status 'Pendente de Aprovação', não diretamente para 'Ativa'."_
- Atualizar CA-044.15 para refletir o comportamento diferenciado

---

### QA-044-04 🔴 `[LACUNA]` Inativação não define cascata nos agentes vinculados

**Onde:** RF-044.42 a RF-044.44  
**Problema:** A suspensão (RN-044.04) bloqueia agentes em cascata. A inativação não menciona esse comportamento — os agentes ficam em "limbo". CA-044.15 menciona que reativar "libera os agentes", mas não há regra de "bloqueio ao inativar".

**Resolução:**

- Adicionar RN-044.19: _"Ao inativar uma agência, todos os agentes vinculados têm seus acessos bloqueados automaticamente (status operacional: bloqueado). Ao reativar, os acessos são restabelecidos automaticamente."_
- Decidir com o negócio: os agentes voltam todos automaticamente ou cada um deve ser reativado manualmente para garantir que apenas os atuais tenham acesso?

---

### QA-044-05 🔴 `[LACUNA]` Soft delete não define destino dos agentes vinculados

**Onde:** RF-044.46  
**Problema:** Ao excluir uma agência via soft delete, o que acontece com os agentes vinculados? Ficam órfãos no sistema? Isso pode causar erros de ponteiro nulo em relatórios e buscas.

**Resolução:**

- Adicionar RN-044.20: _"Ao realizar soft delete de uma agência, o sistema deve aplicar soft delete em cascata em todos os agentes vinculados. Os históricos financeiros e de vendas permanecem preservados e acessíveis ao Administrador via filtro 'Excluídos'."_
- Adicionar campo `motivo_exclusao` e `excluido_por` (auditoria) na operação de exclusão
- Definir prazo de retenção antes do expurgo definitivo (ex: 90 dias)

---

### QA-044-06 🟡 `[LACUNA]` Aba "Todas" com seleção mista não definida

**Onde:** Tabela "Barra de Ações por Aba"  
**Problema:** Comportamento ao selecionar agências de status diferentes na aba "Todas" não está especificado.

**Resolução:**

- Adicionar regra: _"Na aba 'Todas', ao selecionar registros de status diferentes, o sistema exibe apenas ações comuns a todos os status selecionados. Ações exclusivas de um status ficam desabilitadas com tooltip explicativo."_

---

### QA-044-07 🟡 `[CONFLITO]` Reativação e estado do contrato (RN-044.08 vs RN-044.15)

**Onde:** RN-044.08 + RN-044.15  
**Problema:** Uma agência inativada por quebra de contrato pode ser reativada diretamente para "Ativa". Se o contrato anterior foi rescindido, ela volta a operar sem novo contrato?

**Resolução:**

- Adicionar RN-044.21: _"Ao reativar uma agência previamente inativada, o sistema verifica o status do Contrato de Agência em RF-008. Se o contrato estiver rescindido ou expirado, a agência retorna ao status 'Aprovada — Aguardando Contrato', exigindo novo contrato antes de operar."_

---

## RF-045 — Cadastro de Agência

### QA-045-01 🔴 `[CONFLITO]` RF-045.40 vs RN-044.14/15 — Cadastro manual cria "Ativa" sem contrato

**Onde:** RF-045.40 + RN-044.14 + RN-044.15  
**Problema:** RF-045.40 registra a agência como "Ativa" imediatamente no cadastro manual. RN-044.15 impede operação sem contrato assinado. Há um intervalo em que a agência está "Ativa" mas não pode operar — sem indicação clara disso para o Admin.

**Resolução:**

- Alterar RF-045.40: _"Após cadastro criado pelo Admin, o sistema deve registrar a agência com status 'Aprovada — Aguardando Contrato' e gerar automaticamente o rascunho de Contrato de Agência em RF-008."_
- Remover a contradição com RN-044.15

---

### QA-045-02 🔴 `[NOVO REQUISITO]` CNPJ alfanumérico a partir de julho/2026

**Onde:** RF-045.12 + RN-045.01 + RN-045.11  
**Problema:** A Receita Federal alterará o formato do CNPJ para alfanumérico (letras e números) a partir de julho/2026. A validação atual por dígitos verificadores e máscara numérica ficará obsoleta.

**Resolução:**

- Adicionar RN-045.13: _"O sistema deve suportar os dois formatos de CNPJ: numérico (formato atual XX.XXX.XXX/XXXX-XX) e alfanumérico (novo formato a partir de julho/2026). A validação deve verificar o formato aplicável conforme a data de emissão do CNPJ e o algoritmo de verificação correspondente."_
- Atualizar máscara do campo RF-045.12 para aceitar letras e números
- Previsto no roadmap técnico como ajuste obrigatório antes de julho/2026

---

### QA-045-03 🔴 `[CONFLITO]` CA-045.07 bypassa fluxo de aprovação e contrato

**Onde:** CA-045.07  
**Problema:** O Admin pode mudar o status de "Pendente" para "Ativa" diretamente pela edição do cadastro, bypassando o fluxo de aprovação do RF-044 (com geração de contrato e e-mail de boas-vindas com credenciais).

**Resolução:**

- Remover a possibilidade de alterar status via edição de cadastro
- O status só deve ser alterado via fluxo formal de aprovação em RF-044
- Ou, se mantida, garantir que o mesmo fluxo de geração de contrato e notificação seja acionado

---

### QA-045-04 🟡 `[AMBIGUIDADE]` Upload de documentos: Etapa 1 "ou" etapa adicional

**Onde:** RF-045.32  
**Problema:** O uso de "ou" deixa a decisão em aberto para o desenvolvedor. Uma 4ª etapa contradiria RF-045.01 que define apenas 3 etapas.

**Resolução:**

- Definir explicitamente: os uploads ficam em uma **Etapa 4 — Documentos**, adicionada apenas no fluxo de auto-cadastro
- Atualizar RF-045.01: _"No fluxo de auto-cadastro, o formulário possui quatro etapas: Etapa 1 — Dados da Empresa, Etapa 2 — Dados do Responsável, Etapa 3 — Dados Bancários, Etapa 4 — Documentos."_

---

## RF-046 — Gestão de Agentes

### QA-046-01 🔴 `[LACUNA]` Transferência de agente: histórico de vendas e atrações

**Onde:** RF-046.41 a RF-046.43  
**Problema:** Após transferência para nova agência:

- As vendas anteriores são contabilizadas na nova agência ou permanecem na antiga?
- O agente passa a vender apenas produtos da nova agência ou ainda vende da anterior?
- As comissões acumuladas da agência anterior ficam com ela?

**Resolução:**

- Adicionar RN-046.14: _"Comissões geradas por vendas realizadas antes da transferência pertencem irrevogavelmente à agência de origem, independente da transferência posterior do agente."_
- Adicionar RN-046.15: _"Após a transferência, o agente passa a comercializar exclusivamente as atrações autorizadas pela nova agência. As autorizações da agência anterior são revogadas automaticamente."_
- Adicionar RN-046.16: _"O histórico de vendas anterior à transferência permanece visível ao Administrador e à agência de origem para fins de relatório e comissionamento."_

---

### QA-046-02 🔴 `[LACUNA]` Transferência de agente inativo

**Onde:** RF-046.38  
**Problema:** RF-046.38 permite transferir apenas agentes **ativos**. Não há fluxo para transferir um agente inativo, nem para ativá-lo diretamente na nova agência.

**Resolução:**

- Definir explicitamente: agente inativo deve ser ativado antes da transferência, **ou**
- Adicionar opção: ao transferir um agente inativo, o sistema pergunta se deve ativá-lo na nova agência

---

### QA-046-03 🔴 `[LACUNA]` Agente após soft delete pode se recadastrar com mesmo CPF?

**Onde:** RF-046.16  
**Problema:** Após exclusão de um agente, o histórico financeiro e de vendas deve ser mantido. Mas o CPF do agente excluído ainda está ocupado no sistema? Se um novo agente com mesmo CPF tentar se cadastrar, ocorrerá erro?

**Resolução:**

- Adicionar RN-046.17: _"O soft delete de um agente preserva o CPF como ocupado no sistema para fins de integridade histórica. Um novo cadastro com o mesmo CPF só é permitido após análise e autorização explícita do Administrador."_

---

### QA-046-04 🟡 `[LACUNA]` Agente desvinculado: quem pode revincular?

**Onde:** RN-046.05  
**Problema:** Agente desvinculado fica "Inativo até novo vínculo", mas não há especificação de quem pode criar esse novo vínculo — outra agência pode vincular esse agente?

**Resolução:**

- Adicionar RN-046.18: _"Um agente desvinculado (status Inativo) pode ser vinculado a outra agência pelo Administrador ou pelo perfil Agência via fluxo 'Adicionar Agente' informando o CPF/e-mail do agente existente. O sistema deve identificar o cadastro e oferecer a opção de vínculo."_

---

### QA-046-05 🟡 `[LACUNA]` Inativação de agência não bloqueia login do agente no app

**Onde:** RF-044.36 + RF-046  
**Problema:** RN-044.04 diz que agentes de agência suspensa ficam "impedidos de realizar vendas", mas não menciona se o login deles no app/portal é bloqueado ou se podem entrar apenas para ver o histórico.

**Resolução:**

- Definir claramente: agente de agência suspensa/inativada tem acesso bloqueado completamente, ou acesso somente leitura ao histórico?
- Sugestão: acesso bloqueado para vendas, mas permitir leitura do histórico pessoal

---

## RF-047 — Operação Comercial

### QA-047-01 🔴 `[LACUNA]` Perfis autorizados a cancelar venda não definidos

**Onde:** RF-047.22 a RF-047.26  
**Problema:** Não está explícito quais perfis podem acionar o botão "Cancelar Venda". Os 3 perfis (Agente, Agência, Administrador) podem cancelar? A Agência pode cancelar venda de um agente dela?

**Resolução:**

- Adicionar tabela de permissões de cancelamento:

|Perfil|Pode cancelar próprias vendas|Pode cancelar vendas de agentes vinculados|
|---|---|---|
|Agente|✅|❌|
|Agência|✅|✅|
|Administrador|✅|✅|

- Adicionar RN-047.12: _"Quando a Agência cancelar uma venda de um agente vinculado, o sistema deve enviar notificação ao agente informando o cancelamento e o motivo."_

---

### QA-047-02 🟡 `[LACUNA]` Cancelamento parcial de pedido não previsto

**Onde:** RF-047.23 a RF-047.25  
**Problema:** Um pedido pode ter múltiplos ingressos. Não está definido se é possível cancelar apenas um ingresso do pedido (cancelamento parcial) ou se o cancelamento é sempre do pedido inteiro.

**Resolução:**

- Definir explicitamente:
    - **Opção A:** Cancelamento é sempre do pedido inteiro
    - **Opção B:** É possível cancelar ingressos individuais dentro do pedido
- Se Opção B: especificar como o estorno parcial é calculado e como o QR Code do ingresso cancelado é invalidado sem afetar os demais

---

### QA-047-03 🟡 `[LACUNA]` Histórico de agente transferido na visão da Agência

**Onde:** RN-047.02  
**Problema:** A Agência vê vendas de todos os seus agentes vinculados. Após transferência de um agente, a agência anterior ainda vê as vendas históricas desse agente? E a nova agência vê o histórico anterior?

**Resolução:**

- Adicionar RN-047.13: _"A Agência visualiza apenas as vendas realizadas pelos agentes durante o período em que estavam vinculados a ela. Vendas anteriores ao vínculo ou posteriores à transferência não são visíveis."_

---

### QA-047-04 🟡 `[LACUNA]` Seção de cupons: visibilidade para o Agente

**Onde:** RF-047.27 a RF-047.29  
**Problema:** A seção "Cupons Emitidos pela Agência" não define se o Agente também a visualiza, e se sim, com quais restrições.

**Resolução:**

- Definir: Agente não vê a seção de cupons (são cupons da agência, não do agente)
- Ou: Agente vê somente leitura os cupons que tem autorização de utilizar
- Adicionar RN-047.14 com a definição adotada

---

## RF-048 — Comissionamento e Repasse

### QA-048-01 🔴 `[CONFLITO]` Botão "Contestar" ausente para status "Repasse Solicitado"

**Onde:** RF-048.10 + RN-048.08  
**Problema:** RN-048.08 permite contestar quando o período está "Fechado" **ou** "Repasse Solicitado". RF-048.10 exibe o botão "Contestar" apenas para períodos com status "Fechado".

**Resolução:**

- Atualizar RF-048.10: _"O sistema deve exibir botão 'Contestar' na linha de cada período com status 'Fechado' ou 'Repasse Solicitado', enquanto o repasse ainda não foi pago."_

---

### QA-048-02 🔴 `[LACUNA]` Agente não pode contestar comissão recebida incorretamente

**Onde:** RF-048.24 + RN-048.09  
**Problema:** O agente não tem acesso ao botão "Contestar" nem ao formulário de contestação. Mas se o agente recebeu comissão incorreta (ex.: 10% ao invés de 15%), ele não tem como reclamar pela plataforma.

**Resolução:**

- Adicionar funcionalidade de **"Reportar Divergência"** na visão do Agente, mais simples que contestação formal:
- Adicionar RF-048.X: _"O sistema deve exibir botão 'Reportar Divergência' na tabela de comissões do Agente, que abre formulário com campo de transação, valor esperado e descrição, enviando notificação à Agência e ao Administrador."_

---

### QA-048-03 🔴 `[LACUNA]` Agente transferido: como recebe comissões da agência anterior?

**Onde:** RN-048.09  
**Problema:** O repasse é sempre feito para a agência atual do agente. Se o agente foi transferido antes do fechamento do período, quem recebe as comissões das vendas anteriores?

**Resolução:**

- Adicionar RN-048.13: _"A comissão gerada por uma venda pertence irrevogavelmente à Agência à qual o Agente estava vinculado no momento da venda. A transferência do Agente para outra agência não altera o destinatário do repasse de comissões retroativas."_

---

### QA-048-04 🟡 `[LACUNA]` Erro identificado pelo Administrador após fechamento do período

**Onde:** RF-048.34 a RF-048.36  
**Problema:** Não há botão "Reabrir Período" ou "Estornar Fechamento" para o Administrador corrigir erros após o fechamento.

**Resolução:**

- Adicionar RF-048.X: _"O Administrador deve ter acesso a botão 'Lançamento Avulso' para registrar créditos ou débitos de correção no período subsequente (em aberto), sem reabrir o período fechado."_
- Adicionar RN-048.14: _"Erros identificados em períodos com status 'Fechado' ou 'Repasse Pago' não podem ser alterados retroativamente. A correção é aplicada via lançamento avulso no próximo período em aberto, com registro obrigatório de justificativa."_

---

### QA-048-05 🟡 `[LACUNA]` Agente não recebe notificação de repasse pago

**Onde:** CU-034 passo 7  
**Problema:** Ao confirmar o repasse, apenas a Agência é notificada. O Agente não recebe notificação que suas comissões foram pagas.

**Resolução:**

- Atualizar RN-048.12: _"Notificações automáticas devem ser enviadas: à Agência ao ter repasse autorizado ou rejeitado; ao Agente ao ter suas comissões incluídas em repasse pago; ao Administrador ao receber nova solicitação ou contestação."_

---

### QA-048-06 🟡 `[NOVO REQUISITO]` Coluna de detalhamento de comissão para conferência

**Onde:** RF-048.26  
**Problema:** A lista de repasses não exibe detalhamento suficiente para verificar se a taxa de comissão foi aplicada corretamente (ex.: 15% configurado vs 10% aplicado).

**Resolução:**

- Adicionar coluna opcional na tabela: Tipo de Ingresso | Valor da Venda | % Comissão Configurada | Valor Comissão Calculado
- Adicionar RN-048.15: _"O sistema deve permitir ao Administrador e à Agência expandir o detalhamento de cada período para verificar a taxa de comissão aplicada por transação, comparando com a taxa configurada em RF-010."_

---

### QA-048-07 🟡 `[LACUNA]` Reembolso parcial: impacto na comissão da Agência

**Onde:** RN-048.04 + RF-049  
**Problema:** Se um ingresso custou R$100 e gerou R$10 de comissão, e o Admin aprova reembolso parcial de R$40, o que acontece com a comissão?

**Resolução:**

- Adicionar RN-048.16: _"Em caso de reembolso parcial aprovado em RF-049, a comissão é recalculada proporcionalmente sobre o valor retido (não reembolsado). A diferença entre a comissão original e a recalculada é lançada como dedução no período corrente ou subsequente, conforme o status do período."_

---

## RF-049 — Fila de Reembolsos

### QA-049-01 🔴 `[CONFLITO]` Critério de entrada na fila: 24h (RF-047) vs 7 dias (RF-049)

**Onde:** RF-047.26 + RN-049.02  
**Problema:** RF-047.26 redireciona cancelamentos após 24h para RF-049. RN-049.02 diz que entram na fila solicitações com mais de 7 dias da compra. O intervalo entre 24h e 7 dias não está coberto por nenhum fluxo.

**Resolução:**

- Atualizar RN-049.02: _"Entram na fila de reembolsos: (a) solicitações manuais realizadas após 24h da compra que não se enquadram no reembolso automático de RF-040; (b) solicitações de Agentes ou Agências após o prazo de cancelamento regulamentar."_
- O critério de 7 dias da RN-049.02 refere-se ao reembolso **automático** de RF-040, não à entrada na fila manual

---

### QA-049-02 🔴 `[NOVO REQUISITO]` Origem da solicitação de reembolso não registrada

**Onde:** RF-049  
**Problema:** O sistema não registra se a solicitação veio do Turista, Agente, Agência ou Administrador.

**Resolução:**

- Adicionar RN-049.17: _"O sistema deve registrar a origem de cada solicitação de reembolso, categorizando-a como: Turista (auto-solicitação), Agente, Agência ou Administrador (cancelamento mandatório)."_
- Adicionar coluna "Origem" na tabela da fila (RF-049.12)

---

### QA-049-03 🔴 `[NOVO REQUISITO]` Cancelamento mandatório pelo Administrador não previsto

**Onde:** RF-049  
**Problema:** Não há fluxo para cancelamentos iniciados pelo próprio Administrador por motivos de força maior, overbooking ou falha técnica — esses deveriam ser processados imediatamente sem passar pela fila.

**Resolução:**

- Adicionar RN-049.18: _"Cancelamentos iniciados pelo Administrador por motivos de força maior, overbooking ou segurança técnica são processados de forma mandatória e imediata: estorno integral ao turista, cancelamento de todas as comissões provisionadas na cadeia de intermediários, sem transitar pela fila de reembolsos."_

---

### QA-049-04 🟡 `[LACUNA]` Bloqueio "Em Análise" não define comportamento visual para outros Admins

**Onde:** RN-049.09  
**Problema:** O status "Em Análise" bloqueia ações paralelas de outros Administradores, mas não especifica o que eles veem ao tentar acessar o item bloqueado.

**Resolução:**

- Atualizar RN-049.09: _"Ao tentar acessar item com status 'Em Análise' por outro Administrador, o sistema deve exibir o modal em modo somente leitura com indicação de qual Administrador está analisando e desde quando."_

---

### QA-049-05 🟡 `[NOVO REQUISITO]` Política de cancelamento da atração não exibida no modal

**Onde:** Modal de Decisão (RF-049.31)  
**Problema:** O Admin toma a decisão de aprovar/rejeitar sem acesso às regras comerciais de cancelamento da atração vigentes na data da compra.

**Resolução:**

- Adicionar RN-049.20: _"O modal de decisão deve exibir as regras comerciais de cancelamento da atração vigentes na data da compra (política de reembolso configurada pelo Parceiro Comercial), servindo como referência para a decisão do Administrador."_

---

## RF-050 — CMS Institucional

### QA-050-01 🟡 `[LACUNA]` Inativação de categoria não avisa sobre ocultação das perguntas

**Onde:** CA-050.09  
**Problema:** Ao inativar uma categoria, suas perguntas são ocultadas automaticamente no portal, mas o Admin não recebe aviso sobre isso no momento da inativação.

**Resolução:**

- Atualizar modal de confirmação de inativação para exibir: _"Esta categoria possui X perguntas ativas. Ao inativá-la, todas as perguntas também serão ocultadas do portal. Deseja continuar?"_

---

### QA-050-02 🟢 `[LACUNA]` Sem CA testando remoção da versão mais antiga ao atingir limite

**Onde:** RN-050.04  
**Problema:** Não há critério de aceitação validando o comportamento quando a 21ª versão é salva.

**Resolução:**

- Adicionar CA-050.16: _"Salvar a 21ª versão de uma seção com histórico cheio (20 versões). Resultado esperado: A versão mais antiga é removida automaticamente; o histórico mantém exatamente 20 versões."_
- Adicionar RN-050.13: _"Apenas publicações oficiais geram nova entrada no histórico de versões. Rascunhos consecutivos sobrescrevem o rascunho anterior sem criar nova versão."_

---

### QA-050-03 🟢 `[NOVO REQUISITO]` Limpeza de mídia ao substituir imagem

**Onde:** RF-050.36 + RF-050.37  
**Problema:** Ao substituir foto de membro da equipe ou logo de parceiro, o arquivo anterior permanece no storage gerando acúmulo de arquivos órfãos.

**Resolução:**

- Adicionar RN-050.12: _"Ao atualizar a foto de um membro da equipe ou logo de parceiro, o sistema deve deletar permanentemente o arquivo anterior do storage."_

---

## RF-051 — CMS Home e Curadoria

### QA-051-01 🟡 `[LACUNA]` Reordenação de banners com limite excedido não definida

**Onde:** RF-051.11 + RF-051.15  
**Problema:** Se via drag-and-drop um banner que estava além do limite de 5 passar para as primeiras posições, ele passa a ser exibido automaticamente?

**Resolução:**

- Adicionar RN-051.13: _"A ordem dos banners determina prioridade de exibição. Apenas os primeiros N banners ativos (conforme limite configurado) são exibidos no portal. Ao reordenar, o sistema recalcula automaticamente quais banners estão dentro e fora do limite, exibindo indicador visual na listagem."_

---

### QA-051-02 🟡 `[LACUNA]` Limite de atrações no cross-sell automático não definido

**Onde:** RN-051.07  
**Problema:** O modo automático não define quantas atrações são sugeridas, o que pode quebrar o layout do frontend.

**Resolução:**

- Adicionar RN-051.12: _"No modo Automático, o sistema retorna no máximo 4 atrações sugeridas, priorizando primeiro a mesma categoria e, como critério de desempate, a menor distância geográfica (raio máximo de 50km)."_

---

### QA-051-03 🟢 `[LACUNA]` Sem CA para troca de periodicidade de sincronização Google

**Onde:** RF-051.27  
**Problema:** Nenhum critério de aceitação valida a configuração de periodicidade de sincronização.

**Resolução:**

- Adicionar CA-051.17: _"Alterar periodicidade de sincronização de 'Diária' para 'Semanal'. Resultado esperado: Configuração salva; próxima sincronização programada para 7 dias após a última."_
- Adicionar RN-051.14: _"As avaliações do Google devem ser armazenadas em cache local. A API do portal consome exclusivamente os dados cacheados, respeitando a periodicidade configurada em RF-051.27."_

---

### QA-051-04 🟢 `[NOVO REQUISITO]` Validação de conflito de janelas temporais em banners

**Onde:** RN-051.04  
**Problema:** Ao agendar um banner, o sistema não valida se ele causará violação do limite de 5 banners simultâneos no período agendado.

**Resolução:**

- Adicionar CA-051.18: _"Tentar agendar banner cujo período de vigência coincide com outros 5 banners já ativos. Resultado esperado: Sistema bloqueia a operação e exibe mensagem 'O limite de banners simultâneos será violado no período escolhido. Ajuste as datas ou desative um banner existente.'"_

---

## RF-052 — Central de Notificações

### QA-052-01 🔴 `[CONFLITO]` + `[SEGURANÇA/LGPD]` RF-052.24 vs RN-052.03 — "Obrigatório" para marketing viola LGPD

**Onde:** RF-052.24 + RN-052.03  
**Problema:** RF-052.24 permite marcar qualquer regra como "Obrigatório" (ignora opt-in). RN-052.03 diz que marketing sempre respeita opt-in. Se o Admin usar "Obrigatório" em evento de marketing, configura infração à LGPD.

**Resolução:**

- Atualizar RF-052.24: _"A opção 'Obrigatório' está disponível exclusivamente para eventos da categoria Transacional. Para eventos de Marketing/Opt-in, o campo é fixado em 'Respeita opt-in' e não pode ser alterado."_
- Adicionar RN-052.13: _"A condição 'Obrigatório' está disponível exclusivamente para eventos Transacionais. Eventos de Marketing/Opt-in sempre respeitam as preferências do turista (RF-038), sem exceção e sem possibilidade de sobreposição pelo Administrador."_
- Atualizar RN-052.03 com referência cruzada à RN-052.13

---

### QA-052-02 🔴 `[LACUNA]` Segmentação de campanhas sem filtro por opt-in ativo

**Onde:** RF-052.30  
**Problema:** A segmentação não inclui filtro por "turistas com opt-in ativo para marketing", podendo gerar tentativas de envio para quem não consentiu, aumentando a carga de exclusões.

**Resolução:**

- Adicionar opção na segmentação: "Apenas turistas com opt-in ativo para esta categoria"
- Atualizar RF-052.31 para refletir que a estimativa de alcance considera apenas destinatários elegíveis (com opt-in)

---

### QA-052-03 🟡 `[LACUNA]` Status "Rascunho" de campanha não tem fluxo definido

**Onde:** RF-052.34  
**Problema:** O status "Rascunho" aparece na listagem de campanhas, mas não há RF definindo quando uma campanha vira rascunho, se pode ser salva como rascunho antes de confirmar, ou se um rascunho pode ser editado e reaproveitado.

**Resolução:**

- Adicionar RF-052.X: _"O sistema deve exibir botão 'Salvar como Rascunho' no formulário de criação de campanha, permitindo salvar sem confirmar o envio."_
- Adicionar RF-052.X: _"O sistema deve exibir botão 'Duplicar' por campanha, criando cópia com status 'Rascunho' por padrão."_
- Adicionar RN-052.14: _"Campanhas com status 'Cancelada' ou 'Enviada' podem ser duplicadas. A cópia é criada com status 'Rascunho', sem data de envio e com os mesmos template e segmentação da original."_

---

### QA-052-04 🟡 `[LACUNA]` Templates excluídos sem status definido na listagem e sem CA

**Onde:** RN-052.12 + RF-052.34  
**Problema:** Templates excluídos aparecem como `[Excluído]` no histórico, mas não há status definido para filtro, nem CA cobrindo esse cenário. Não está claro se templates excluídos podem ser duplicados (para reaproveitamento).

**Resolução:**

- Adicionar CA-052.16: _"Excluir template ativo e verificar histórico de envios vinculado. Resultado esperado: Template aparece como '[Excluído]' no histórico; dados de envio preservados."_
- Definir: template excluído pode ser duplicado? Sugestão: sim, pois gera cópia com status Inativo
- Adicionar filtro "Excluídos" nos filtros do histórico (RF-052.38)

---

### QA-052-05 🟢 `[LACUNA]` RN-052.06 não distingue tipo de campanha (e-mail vs push)

**Onde:** RN-052.06  
**Problema:** RN-052.06 exige e-mail verificado para campanhas, mas não distingue entre campanhas de e-mail e push. Para campanhas push, o critério relevante é o consentimento explícito (RN-052.07), não o e-mail verificado.

**Resolução:**

- Atualizar RN-052.06: _"Campanhas do tipo E-mail são enviadas apenas para turistas com e-mail verificado. Campanhas do tipo Push requerem consentimento explícito de push (RN-052.07), independente do status de verificação de e-mail."_

---

## RF-056 — Tela Inicial por Perfil

### QA-056-01 🔴 `[CONFLITO]` Leitor tem "Validar Ingresso" que é uma ação, não leitura

**Onde:** RF-056.23 + RF-056.25  
**Problema:** RF-056.25 define o Leitor como somente leitura. RF-056.23 dá acesso ao módulo "Validar Ingresso" que é uma ação (escanear QR Code e registrar entrada). Há contradição direta.

**Resolução:**

- Definir explicitamente: o Leitor pode validar ingressos (ação de entrada) apesar do nome "somente leitura"?
- **Opção A:** Renomear o perfil para "Operador" ou criar exceção explícita em RF-056.25: _"exceto pela ação de validação de ingresso (RF-025), que é permitida."_
- **Opção B:** Remover "Validar Ingresso" do menu do Leitor, deixando apenas para o Editor

---

### QA-056-02 🔴 `[LACUNA]` Administrador não tem tela inicial definida para módulos compartilhados

**Onde:** RF-056 (tabela de menus) + RF-047 + RF-048  
**Problema:** RF-056 não inclui o Administrador na tabela de menus. O Admin acessa RF-047 e RF-048 (módulos compartilhados com Agência/Agente), mas não há especificação de como ele visualiza esses módulos.

**Resolução:**

- Adicionar seção "Administrador" na tabela de menus do RF-056 com nota referenciando RF-002/RF-003
- Especificar em RF-047 e RF-048 o comportamento da visão do Admin (já parcialmente coberto em RF-047.32/33 e RF-048.25+)
- Garantir que RF-002 cubra a navegação do Admin em todos os módulos compartilhados

---

### QA-056-03 🟡 `[LACUNA]` Editor e Leitor sem atração vinculada: sem fluxo de exceção

**Onde:** RN-056.04 + RN-056.05 + CU-039  
**Problema:** CU-039 tem fluxo de exceção para Parceiro Comercial sem atrações (3b), mas não para Editor ou Leitor sem atração vinculada.

**Resolução:**

- Adicionar fluxo de exceção 3c no CU-039: _"Editor ou Leitor sem atração vinculada: Sistema exibe mensagem informativa 'Nenhuma atração vinculada ao seu perfil. Entre em contato com o Parceiro Comercial responsável.' e bloqueia acesso aos módulos dependentes de atração."_

---

### QA-056-04 🟢 `[NOMENCLATURA]` "Gráficos Analytics" vs "Gráficos e Analytics"

**Onde:** RF-056.12 + RF-056.18  
**Problema:** O mesmo módulo (RF-019) tem dois nomes diferentes no documento.

**Resolução:**

- Padronizar para **"Gráficos e Analytics"** em todos os RFs que referenciam RF-019

---

### QA-056-05 🟢 `[LACUNA]` Sem CA testando persistência do menu entre sessões diferentes

**Onde:** RN-056.11 + CA-056.12  
**Problema:** CA-056.12 testa persistência apenas dentro da mesma sessão. RN-056.11 exige persistência entre sessões diferentes.

**Resolução:**

- Adicionar CA-056.16: _"Recolher menu lateral, encerrar sessão, fazer login novamente. Resultado esperado: Menu permanece recolhido conforme estado salvo na sessão anterior."_

---

## RF-057 — Gestão de Parceiros Comerciais

### QA-057-01 🔴 `[CONFLITO]` Parceiro rejeitado pode ser reativado sem nova aprovação

**Onde:** RF-057.32 + RN-057.08  
**Problema:** Mesmo problema do RF-044: parceiro rejeitado recebe status "Inativa" e pode ser reativado diretamente para "Ativa" sem nova aprovação, pois RN-057.08 não distingue rejeitados de inativados.

**Resolução:**

- Adicionar RN-057.17: _"Parceiros com histórico de rejeição (nunca aprovados) ao serem reativados devem retornar ao status 'Pendente de Aprovação', não diretamente para 'Ativa'."_

---

### QA-057-02 🔴 `[LACUNA]` Suspensão não bloqueia o próprio Parceiro Comercial

**Onde:** RF-057.37  
**Problema:** RF-057.37 bloqueia Editores e Leitores vinculados na suspensão, mas não menciona explicitamente se o próprio Parceiro Comercial tem acesso bloqueado.

**Resolução:**

- Atualizar RF-057.37: _"Ao confirmar a suspensão, o acesso do Parceiro Comercial e de todos os Editores e Leitores vinculados ao Backoffice deve ser bloqueado imediatamente."_
- Adicionar RN-057.18: _"A suspensão bloqueia o acesso ao Backoffice para o Parceiro Comercial e todos os usuários vinculados (Editores e Leitores). Nenhuma operação comercial pode ser realizada durante a suspensão."_

---

### QA-057-03 🔴 `[LACUNA]` Soft delete não define destino das atrações vinculadas

**Onde:** RF-057.47  
**Problema:** Ao excluir um parceiro, o destino das atrações vinculadas não está definido — ficam órfãs? São inativadas? O que acontece com Editores e Leitores dessas atrações?

**Resolução:**

- Adicionar RN-057.19: _"Ao realizar soft delete de um Parceiro Comercial, o sistema deve inativar automaticamente todas as atrações vinculadas e bloquear o acesso de todos os Editores e Leitores associados. Os históricos de vendas e contratos são preservados e acessíveis ao Administrador."_

---

### QA-057-04 🔴 `[NOVO REQUISITO]` Sem fluxo para solicitar documentação pendente sem rejeitar

**Onde:** RF-057.16  
**Problema:** O Admin só pode "Aprovar" ou "Rejeitar" um parceiro pendente. Se falta documentação, ele precisa rejeitar e o parceiro perde o status de pendente — não há opção de notificar o parceiro e manter pendente para complementação.

**Resolução:**

- Adicionar ação **"Solicitar Complementação"** na barra de ações da aba "Pendente de Aprovação"
- Adicionar RF-057.X: _"Na aba 'Pendente de Aprovação', o sistema deve exibir botão 'Solicitar Complementação' que abre modal com campo de texto descrevendo a pendência. O sistema envia notificação ao parceiro por e-mail e mantém o status 'Pendente de Aprovação'."_
- Adicionar CA-057.20: _"Admin aciona 'Solicitar Complementação' com descrição da pendência. Resultado esperado: E-mail enviado ao parceiro; status permanece 'Pendente de Aprovação'; pendência registrada no histórico do cadastro."_

---

### QA-057-05 🟡 `[LACUNA]` Contrato gerado antes da atração existir

**Onde:** RF-057.28 + RN-057.14  
**Problema:** O contrato é gerado automaticamente na aprovação, mas no momento da aprovação a atração pode não existir ainda. O contrato seria gerado com campos de atração em branco.

**Resolução:**

- Atualizar RN-057.14: _"O Contrato de Atração gerado automaticamente na aprovação é pré-preenchido com os dados cadastrais do parceiro. Os campos referentes à atração específica ficam em branco e devem ser complementados pelo Admin em RF-008 após o cadastro da primeira atração pelo Parceiro Comercial."_

---

### QA-057-06 🟡 `[LACUNA]` Estado intermediário entre aprovação e contrato assinado no cadastro manual

**Onde:** RN-057.15 + RN-057.16  
**Problema:** No cadastro manual (RN-057.16), o parceiro é criado como "Ativa" diretamente, mas RN-057.15 diz que sem contrato assinado as atrações não podem operar. O estado intermediário não está definido.

**Resolução:**

- Implementar conceito de **Substatus de Operação por Atração**:
    - `Bloqueado para Vendas` (padrão ao criar atração)
    - `Liberado para Vendas` (alterado automaticamente quando contrato atinge status "Ativo" em RF-008)
- Adicionar RN-057.20: _"O status do Parceiro Comercial (Ativo/Inativo) controla o direito de autenticação. A permissão de venda é controlada por um Substatus de Operação de cada atração, independente, alterado automaticamente pelo webhook do DocuSign ao confirmar todas as assinaturas."_

---

### QA-057-07 🟢 `[LACUNA]` CA-057.15 libera Editores/Leitores sem verificar contrato

**Onde:** CA-057.15 + RN-057.15  
**Problema:** Ao reativar um parceiro inativo, Editores e Leitores são liberados. Mas o contrato pode ainda estar pendente — os usuários acessam uma atração que não pode operar.

**Resolução:**

- Atualizar CA-057.15: _"Reativar parceiro inativo. Resultado esperado: Status alterado para 'Ativa'; Editores e Leitores têm acesso restabelecido para leitura; operação comercial permanece bloqueada se o Contrato de Atração não estiver com status 'Ativo' em RF-008."_

---

## Resumo Executivo

|RF|🔴 Alta|🟡 Média|🟢 Baixa|Total|
|---|---|---|---|---|
|RF-044|5|2|0|7|
|RF-045|3|1|0|4|
|RF-046|3|2|0|5|
|RF-047|1|3|0|4|
|RF-048|3|4|0|7|
|RF-049|3|2|0|5|
|RF-050|0|1|2|3|
|RF-051|0|2|2|4|
|RF-052|2|3|1|6|
|RF-056|2|1|2|5|
|RF-057|4|3|1|8|
|**TOTAL**|**26**|**24**|**8**|**58**|

---

## Itens Fora de Escopo dos Requisitos (Recomendações Técnicas)

> Estes itens não são erros de requisito, mas devem ser comunicados ao time de desenvolvimento como restrições técnicas obrigatórias.

|#|RF|Recomendação|
|---|---|---|
|T-01|RF-044/045|CNPJ alfanumérico: preparar validação para o novo formato a partir de julho/2026|
|T-02|RF-049|Coluna SLA deve ser campo calculado em runtime, não salvo no banco (evitar dado obsoleto)|
|T-03|RF-050|Sanitização XSS deve ser feita no backend (não confiar no frontend)|
|T-04|RF-050|Slugs duplicados devem receber sufixo numérico automático (ex: `ingressos-1`)|
|T-05|RF-051|Status de banner expirado deve ser verificado por query dinâmica na API pública, não por atualização manual do painel|
|T-06|RF-051|Avaliações Google devem ser cacheadas localmente; API pública nunca deve bater diretamente na API do Google|
|T-07|RF-056/057|Queries de atração devem incluir `AND parceiro_id = :current_user_id` para evitar vazamento de dados entre parceiros (multi-tenancy)|

---

_Documento gerado em revisão de QA. Todos os itens devem ser triados pelo PO e time técnico antes da próxima sprint de desenvolvimento._