### 3.49 Fila de Reembolsos - Administrador

**ID:** RF-049

Módulo: Gestão de Reembolsos

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo do Backoffice para triagem e processamento manual de solicitações de reembolso que ultrapassaram o prazo de 7 dias para reembolso automático (RF-040) e que estejam fora da janela de cancelamento gratuito estipulada pela atração/comercial. O Administrador visualiza a fila de solicitações pendentes, analisa os detalhes de cada caso — incluindo a origem da solicitação (Turista, Agente, Agência ou Administrador) e as regras comerciais de cancelamento vigentes na data da compra — e aprova (com valor integral ou parcial) ou rejeita (com motivo obrigatório) cada solicitação.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.01 | O sistema deve exibir o título "Fila de Reembolsos" acompanhado de um contador com a quantidade de itens pendentes                            |
| RF-049.02 | O sistema deve exibir campo de busca por ID do pedido, nome do turista ou e-mail do turista                                                   |
| RF-049.03 | O sistema deve exibir botão "Filtro" para acesso aos filtros avançados                                                                        |
| RF-049.04 | O sistema deve exibir abas de status: "Pendentes" (padrão), "Em Análise", "Aprovados", "Rejeitados" e "Todos"                                 |
| RF-049.05 | O sistema deve exibir a aba "Pendentes" selecionada por padrão ao acessar o módulo                                                            |

Campo de Busca e Filtros Avançados

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.06 | O sistema deve permitir busca por ID do reembolso, ID do pedido, nome do turista ou e-mail do turista (case-insensitive)                      |
| RF-049.07 | O painel de filtros avançados deve exibir filtro de Status com seleção múltipla (Pendente, Em Análise, Aprovado, Rejeitado)                   |
| RF-049.08 | O painel de filtros avançados deve exibir filtro de Período da Solicitação com intervalo de datas (data inicial e data final)                 |
| RF-049.09 | O painel de filtros avançados deve exibir filtro de Atração (seleção da atração vinculada ao ingresso)                                       |
| RF-049.10 | O painel de filtros avançados deve exibir filtro de Motivo da Solicitação (lista predefinida de motivos cadastrados pelo turista)             |
| RF-049.11 | O painel de filtros avançados deve exibir filtro de Faixa de Valor com campos de valor mínimo (R$) e valor máximo (R$)                       |
| RF-049.12 | O painel de filtros avançados deve exibir filtro de Origem da Solicitação, com seleção múltipla entre: Turista, Agente, Agência ou Administrador (RN-049.17) |


Tabela da Fila

| ID        | Requisito                                                                                                                                                       |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.13 | A tabela deve exibir as colunas: Checkbox, ID Reembolso, ID Pedido, Turista (nome + e-mail), Atração, Valor (R$), Motivo, Origem, Data Compra, Data Solicitação, SLA, Status |
| RF-049.14 | Todas as colunas devem exibir ícone de ordenação (ASC/DESC) e permitir reordenação                                                                              |
| RF-049.15 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100                                                                  |
| RF-049.16 | Ao clicar em uma linha da tabela (fora do checkbox), o sistema deve abrir o modal de Detalhes e Decisão                                                         |

Indicador de SLA

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.17 | A coluna SLA deve exibir a quantidade de dias em aberto desde a data da solicitação                                                           |
| RF-049.18 | O indicador de SLA deve ser colorido: verde para solicitações com até 3 dias, amarelo de 4 a 7 dias, vermelho para mais de 7 dias             |
| RF-049.19 | A ordenação padrão da tabela deve ser por SLA decrescente para priorizar os casos mais antigos                                                |

Ações em Massa via Checkbox

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.20 | O sistema deve exibir checkbox na primeira coluna para seleção individual e coletiva de solicitações                                          |
| RF-049.21 | Ao selecionar um ou mais itens, o sistema deve exibir barra de ações com contador "Selecionados X"                                            |
| RF-049.22 | A barra de ações em massa deve exibir os botões: "Aprovar selecionados", "Rejeitar selecionados" e "Marcar como Em Análise"                   |
| RF-049.23 | A ação "Rejeitar selecionados" deve exigir preenchimento obrigatório de motivo antes de confirmar                                             |

Modal — Seção 1 — Dados da Solicitação

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.24 | O modal deve exibir os seguintes dados da solicitação: ID Reembolso, ID Pedido, Data da Compra, Data da Solicitação e Dias em Aberto (SLA)    |
| RF-049.25 | O modal deve exibir os seguintes dados de pagamento: Valor Pago (R$) e Forma de Pagamento (Cartão, PIX ou Google Pay)                        |
| RF-049.26 | O modal deve exibir os seguintes dados do turista: Nome completo, E-mail e Telefone                                                           |
| RF-049.27 | Quando a origem da solicitação (RN-049.17) for Agente ou Agência, o modal deve exibir adicionalmente a identificação do usuário solicitante e a justificativa operacional anexada à solicitação (RN-049.19) |
| RF-049.28 | Quando o pedido possuir mais de um ingresso e tiver sido encaminhado via cancelamento parcial (RF-047.26), o modal deve listar cada ingresso elegível individualmente, com checkbox de seleção, permitindo ao Administrador aprovar ou rejeitar o reembolso de cada ingresso separadamente.|

Modal — Seção 2 — Dados do Ingresso

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.29 | O modal deve exibir os dados do ingresso: Atração, Tipo de Ingresso, Data e Hora do Evento (quando aplicável) e QR Code associado            |
| RF-049.30 | O modal deve exibir o status atual do ingresso: Ativo, Utilizado ou Expirado                                                                  |
| RF-049.31 | O modal deve exibir o histórico de uso do ingresso com registro de todos os escaneamentos realizados                                          |

Modal — Seção 3 — Motivo da Solicitação

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.32 | O modal deve exibir o motivo selecionado pelo turista no momento da solicitação (RF-040), proveniente de lista predefinida                    |
| RF-049.33 | O modal deve exibir a observação livre digitada pelo turista no momento da solicitação, quando houver                                         |

Modal — Seção 3.5 — Política de Cancelamento da Atração (Novo)

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.34 | O modal deve extrair e exibir as regras comerciais de cancelamento da atração vigentes na data da compra, como indexador de suporte à decisão do Administrador (RN-049.20) |

Modal — Seção 4 — Decisão

| ID        | Requisito                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.35 | A seção de decisão deve oferecer a opção "Aprovar Reembolso" com campo de valor a reembolsar (padrão: valor integral; editável para reembolso parcial)                |
| RF-049.36 | A seção de aprovação deve exibir campo de método de devolução (automático via gateway ou manual) e campo de observação interna opcional                               |
| RF-049.37 | Ao confirmar a aprovação: o ingresso deve ser invalidado, o estorno processado, e-mail de confirmação enviado ao turista, e o status alterado para "Aprovado"         |
| RF-049.38 | A seção de decisão deve oferecer a opção "Rejeitar Reembolso" com campo de motivo obrigatório (lista predefinida com complemento em campo livre)                     |
| RF-049.39 | A seção de rejeição deve exibir preview do e-mail que será enviado ao turista antes da confirmação                                                                    |
| RF-049.40 | Ao confirmar a rejeição: o status deve ser alterado para "Rejeitado" e e-mail de rejeição enviado ao turista com motivo e canal de contato para contestação           |

Histórico de Ações

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-049.41 | O modal deve exibir no rodapé um log de histórico de ações registrando: quem executou a ação, qual ação foi realizada e data/hora             |
| RF-049.42 | O histórico de ações não deve permitir edição ou exclusão de nenhum registro                                                                  |

Colunas da Tabela

| Coluna           | Conteúdo                   | Ordenável | Observação                                           |
|------------------|----------------------------|-----------|------------------------------------------------------|
| Checkbox         | ☐                          | ❌         | Seleção múltipla                                     |
| ID Reembolso     | ID numérico                | ✅         | Identificador único da solicitação                   |
| ID Pedido        | ID numérico                | ✅         | Pedido de origem do ingresso                         |
| Turista          | Nome + E-mail              | ✅         | Ordena por nome                                      |
| Atração          | Nome da atração            | ✅         | Atração vinculada ao ingresso                        |
| Valor (R$)       | Valor pago formatado       | ✅         | Valor original do pagamento                          |
| Motivo           | Motivo da solicitação      | ✅         | Conforme lista predefinida                           |
| Origem           | Badge de origem            | ✅         | Turista, Agente, Agência ou Administrador (RN-049.17) |
| Data Compra      | DD/MM/AAAA                 | ✅         | Data da compra original                              |
| Data Solicitação | DD/MM/AAAA                 | ✅         | Data em que o turista solicitou o reembolso          |
| SLA              | N dias + indicador colorido | ✅        | Ordenação padrão DESC; verde/amarelo/vermelho        |
| Status           | Badge de status            | ✅         | Pendente, Em Análise, Aprovado, Rejeitado            |

Abas de Status

| Aba         | Descrição                                               | Ações Disponíveis                              |
|-------------|---------------------------------------------------------|------------------------------------------------|
| Pendentes   | Solicitações aguardando análise (padrão)                | Aprovar, Rejeitar, Marcar como Em Análise      |
| Em Análise  | Solicitações em avaliação por algum Administrador       | Aprovar, Rejeitar                              |
| Aprovados   | Solicitações com reembolso aprovado                     | Visualizar detalhes                            |
| Rejeitados  | Solicitações com reembolso rejeitado                    | Visualizar detalhes                            |
| Todos       | Todas as solicitações independentemente do status       | Conforme status de cada item                   |

Motivos Predefinidos de Rejeição

| Motivo                                | Descrição                                                                   |
|---------------------------------------|-----------------------------------------------------------------------------|
| Ingresso já utilizado                 | O QR Code do ingresso foi escaneado antes da solicitação de reembolso       |
| Fora do prazo de cancelamento         | A solicitação ultrapassou o prazo máximo permitido para cancelamento         |
| Evento já realizado                   | O evento/visita vinculado ao ingresso já ocorreu na data programada          |
| Documentação insuficiente             | O turista não forneceu evidências ou justificativa suficiente para o reembolso |

Regras de Negócio

| ID        | Regra                                                                                                                                                                       |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-049.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                                                                  |
| RN-049.02 | Somente solicitações manuais que ultrapassaram o prazo de 7 dias da compra E que estejam fora da janela de cancelamento gratuito estipulada pela atração/comercial aparecem na fila de triagem; reembolsos automáticos (≤ 7 dias) ou dentro da janela de cancelamento gratuito são processados pelo RF-040 sem passar pela fila |
| RN-049.03 | O ingresso só é invalidado após a aprovação do reembolso pelo Administrador; a solicitação do turista não invalida o ingresso automaticamente                               |
| RN-049.04 | O Administrador pode aprovar um reembolso parcial, devolvendo valor menor que o pago (ex.: retendo taxa de serviço); o campo de valor deve aceitar qualquer valor entre R$ 0,01 e o valor integral |
| RN-049.05 | Os motivos predefinidos de rejeição são: ingresso já utilizado, fora do prazo de cancelamento, evento já realizado, documentação insuficiente                               |
| RN-049.06 | Após aprovação, o prazo de estorno ao turista varia conforme o gateway: cartão de crédito de 5 a 30 dias úteis; PIX em até 60 minutos                                      |
| RN-049.07 | O e-mail de aprovação enviado ao turista deve incluir o valor aprovado para devolução e o prazo estimado conforme a forma de pagamento                                      |
| RN-049.08 | O e-mail de rejeição enviado ao turista deve incluir o motivo da rejeição e o canal de contato disponível para contestação                                                  |
| RN-049.09 | O status "Em Análise" indica que um Administrador está avaliando a solicitação, bloqueando ações paralelas de outros usuários para evitar duplicidade de decisões            |
| RN-049.10 | A ação em massa de rejeição exige informação de motivo único aplicado a todos os itens selecionados, com confirmação antes de processar                                     |
| RN-049.11 | O histórico de ações registrado no rodapé do modal não pode ser editado ou excluído por nenhum perfil, incluindo o Administrador                                             |
| RN-049.12 | A busca deve funcionar de forma case-insensitive para todos os campos (ID, nome, e-mail)                                                                                    |
| RN-049.13 | A ordenação padrão da tabela é por SLA decrescente (casos mais antigos no topo) para facilitar a priorização                                                                |
| RN-049.14 | A paginação padrão exibe 10 registros por página                                                                                                                            |
| RN-049.17 | (Origem da Solicitação) O sistema deve registrar a origem da solicitação de reembolso, categorizando-a como: Turista, Agente, Agência ou Administrador                       |
| RN-049.18 | (Cancelamento por Iniciativa do Administrador) Cancelamentos efetuados diretamente pelo perfil Administrador por motivos de força maior, overbooking ou segurança técnica serão processados de forma mandatória e imediata, aplicando estorno integral ao turista e cancelamento total de quaisquer comissões provisionadas para a cadeia de intermediários, sem necessidade de transitar pela Fila de Reembolsos |
| RN-049.19 | (Solicitação por Agentes/Agências pós-SLA) Solicitações de cancelamento efetuadas por Agentes ou Agências após o prazo regulamentar de 7 dias serão enviadas para a Fila de Reembolsos do Administrador (RF-049), contendo obrigatoriamente a identificação do usuário solicitante e justificativa operacional anexa.  |
| RN-049.20 | Ao aprovar um reembolso na fila, o sistema deve acionar a dedução da comissão correspondente conforme RF-048.05 — o valor da comissão é compensado no próximo período de apuração em aberto da Agência e do Agente vinculados à venda original.|
| RN-049.21 | (Visibilidade da Política) O modal de decisão de reembolso deve extrair e exibir as regras comerciais de cancelamento da atração vigentes na data da compra, servindo como indexador de suporte para a tomada de decisão do administrador                                                                 |


Critérios de Aceitação

| ID        | Critério                                                                           | Resultado Esperado                                                                                      |
|-----------|------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| CA-049.01 | Acessar o módulo como Administrador                                                | Tela exibida com aba "Pendentes" selecionada e contador de itens pendentes visível                      |
| CA-049.02 | Visualizar lista de solicitações pendentes                                         | Tabela exibe solicitações com status "Pendente" com todas as colunas e ordenação por SLA decrescente    |
| CA-049.03 | Buscar por ID do pedido existente                                                  | Lista filtrada exibindo apenas a solicitação correspondente ao ID informado                             |
| CA-049.04 | Filtrar solicitações por atração específica                                        | Lista atualizada exibindo apenas solicitações vinculadas à atração selecionada                          |
| CA-049.05 | Verificar indicador de SLA para solicitação com mais de 7 dias                     | Coluna SLA exibe indicador vermelho com quantidade de dias em aberto                                    |
| CA-049.06 | Clicar em uma linha da tabela                                                      | Modal de Detalhes e Decisão abre exibindo todas as seções: Dados da Solicitação, Ingresso, Motivo, Política de Cancelamento da Atração e Decisão |
| CA-049.07 | Aprovar reembolso com valor integral                                               | Ingresso invalidado, estorno processado pelo gateway, e-mail enviado ao turista, status = "Aprovado"    |
| CA-049.08 | Aprovar reembolso com valor parcial (menor que o pago)                             | Sistema aceita valor parcial, processa estorno do valor informado e registra observação interna         |
| CA-049.09 | Tentar rejeitar sem preencher motivo                                               | Sistema exibe mensagem de erro "Motivo obrigatório" e bloqueia a confirmação                            |
| CA-049.10 | Rejeitar solicitação com motivo preenchido                                         | Status alterado para "Rejeitado", e-mail com motivo e canal de contestação enviado ao turista           |
| CA-049.11 | Marcar solicitação como "Em Análise"                                               | Status alterado para "Em Análise" e ação bloqueada para outros Administradores                          |
| CA-049.12 | Selecionar múltiplas solicitações e usar ações em massa                            | Barra de ações exibe contador "Selecionados X" com botões Aprovar, Rejeitar e Em Análise                |
| CA-049.13 | Verificar ingresso após aprovação do reembolso                                     | Ingresso consta com status "Inválido" e QR Code desativado                                              |
| CA-049.14 | Verificar se reembolso automático (≤ 7 dias) aparece na fila                       | Solicitação não listada na fila; processamento realizado automaticamente via RF-040                     |
| CA-049.15 | Navegar entre páginas da tabela com paginação                                      | Sistema exibe próximos registros conforme página selecionada, mantendo filtros e ordenação ativos       |
| CA-049.16 | Tentar solicitar cancelamento de um ingresso que possui o selo/direito de cancelamento gratuito ativo | O sistema desvia o fluxo da fila manual (RF-049), invalida o ingresso imediatamente e dispara o estorno automático via gateway (RF-040) |
| CA-049.17 | Administrador realiza cancelamento mandatório por força maior, overbooking ou segurança técnica | Sistema processa de forma imediata sem passar pela fila, com estorno integral ao turista e cancelamento total das comissões provisionadas |
| CA-049.18 | Agente ou Agência solicita reembolso após o prazo de 7 dias                         | Solicitação aparece na fila com origem "Agente"/"Agência"; modal exibe identificação do solicitante e justificativa operacional anexa |
|CA-049.19 | Pedido com 3 ingressos entra na fila via cancelamento parcial (RF-047.26) | Modal lista os ingressos elegíveis individualmente com checkbox; Administrador seleciona 2 e aprova; apenas os 2 selecionados são invalidados e têm estorno processado; dedução de comissão proporcional registrada no próximo período (RN-049.20)|

Protótipo/Wireframe

Figura - WF-053 - Fila de Reembolsos.png (a definir)
