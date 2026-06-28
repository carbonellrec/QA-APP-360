### 3.48 Comissionamento e Repasse - Agência e Agente

**ID:** RF-048

Módulo: Gestão de Agências > Financeiro / Comissionamento

Perfis com Acesso: Administrador, Agência, Agente

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir o gerenciamento completo do ciclo de comissionamento e repasse financeiro para Agências e Agentes. Isso inclui: visualização de comissões acumuladas por período, fechamento mensal de períodos pelo Administrador, solicitação e autorização de repasses, contestação de valores e notificações automáticas a todos os perfis envolvidos. O perfil Agente, embora não solicite repasse diretamente (RN-048.09), pode reportar divergências de comissão ao Administrador por meio de um canal de contestação simplificado, sem necessidade de intermediação obrigatória pela Agência. A comissão gerada por uma venda permanece vinculada de forma irrevogável à Agência detentora do vínculo do Agente na data da venda, mesmo após eventual transferência do Agente para outra agência.

Requisitos Detalhados

Painel de Comissões — Visão da Agência

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.01 | O sistema deve exibir, para o perfil Agência, um painel de comissões com resumo do período atual em aberto                                       |
| RF-048.02 | O painel deve exibir os seguintes totalizadores do período atual: Comissão Bruta Acumulada, Total de Deduções e Comissão Líquida a Receber        |
| RF-048.03 | O sistema deve exibir a data de início e a data prevista de fechamento do período atual                                                           |
| RF-048.04 | O sistema deve exibir tabela de histórico de períodos fechados com as colunas: Período, Vendas (R$), Qtd Ingressos, Comissão Bruta, Deduções, Comissão Líquida, Status |
| RF-048.05 | A coluna Status deve exibir badge visual com os valores: "Aguardando Fechamento", "Fechado", "Repasse Solicitado", "Em Contestação" ou "Repasse Pago" |
| RF-048.06 | O sistema deve permitir clicar em um período da tabela para expandir o detalhamento por atração e por agente vinculado à Agência                  |
| RF-048.07 | O detalhamento expandido deve exibir: nome da atração, quantidade de ingressos vendidos, valor total vendido e comissão gerada por atração        |
| RF-048.08 | O detalhamento expandido deve exibir também a breakdown por Agente: nome do agente, quantidade de vendas e comissão individual                    |
| RF-048.09 | O sistema deve exibir botão "Solicitar Repasse" na linha de cada período com status "Fechado" e comissão líquida maior que zero                   |
| RF-048.10 | O sistema deve exibir botão "Contestar" na linha de cada período com status "Fechado" enquanto o repasse ainda não foi pago                       |

Detalhamento por Transação (Conferência de Valores)

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.10A | O detalhamento expandido (RF-048.06) deve oferecer, de forma opcional/expansível, a visão por transação individual com as colunas: Ingresso, Valor da Venda, % Comissão Configurada, Valor da Comissão Calculada |
| RF-048.10B | O sistema deve exibir um totalizador de conferência ao final da lista de transações, somando o Valor da Venda e o Valor da Comissão exibidos, permitindo à Agência confrontar o somatório com a Comissão Bruta exibida no resumo do período |
| RF-048.10C | Caso o % de Comissão Calculada de uma transação não corresponda ao percentual configurado para o tipo de ingresso vendido (RF-010), o sistema deve sinalizar visualmente a linha (ex.: ícone de alerta) durante o período com status "Aguardando Fechamento", permitindo identificação do erro antes da consolidação |

Contestação de Comissão (Agência)

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.16 | Ao clicar em "Contestar", o sistema deve abrir formulário de contestação com a lista de transações (pedidos) do período                          |
| RF-048.17 | O formulário deve permitir selecionar uma ou mais transações a serem contestadas                                                                  |
| RF-048.18 | O formulário deve exibir campo obrigatório "Motivo da Contestação" e campo "Valor Esperado"                                                      |
| RF-048.19 | Ao enviar a contestação, o sistema deve alterar o status do período para "Em Contestação" e enviar notificação ao Administrador                  |
| RF-048.20 | O sistema deve registrar histórico de contestações com data, motivo, autor da contestação (Agência ou Agente) e status de resolução (Aprovada Total / Aprovada Parcialmente / Rejeitada) |

Painel de Comissões — Visão do Agente

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.21 | O sistema deve exibir, para o perfil Agente, painel simplificado com resumo das comissões individuais acumuladas no período atual                |
| RF-048.22 | O sistema deve exibir tabela de vendas do Agente com comissão por transação: Data, Atração, Ingresso, Valor da Venda, % Comissão, Valor Comissão |
| RF-048.23 | O sistema deve exibir tabela de histórico de períodos fechados com: Período, Vendas (R$), Comissão Bruta, Deduções, Comissão Líquida e Status    |
| RF-048.24 | O perfil Agente **não** deve ter acesso ao botão "Solicitar Repasse" nem ao formulário de contestação completo da Agência (seleção múltipla de transações e valor esperado), mas deve ter acesso a um botão "Reportar Divergência" (vide RF-048.24A) |
| RF-048.24A | O sistema deve exibir, na tabela de vendas do Agente (RF-048.22), um botão "Reportar Divergência" por transação, permitindo ao Agente sinalizar diretamente ao Administrador uma possível divergência no valor da comissão recebida, sem depender de intermediação da Agência |
| RF-048.24B | Ao reportar uma divergência, o sistema deve exibir modal com campo obrigatório "Motivo/Descrição da Divergência" e campo opcional "Valor Esperado pelo Agente" |
| RF-048.24C | Ao confirmar o reporte, o sistema deve registrar a divergência com status "Reportada", vinculá-la à transação e ao período correspondente, e notificar o Administrador e a Agência à qual o Agente está vinculado |
| RF-048.24D | O Administrador deve poder resolver o reporte do Agente com uma das resoluções: Aprovada Total, Aprovada Parcialmente (informando novo valor) ou Rejeitada (com motivo), notificando o Agente e a Agência sobre o resultado |

Visão do Administrador — Gestão de Repasses

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.25 | O sistema deve exibir, para o Administrador, tela de gestão de repasses com lista de solicitações pendentes                                      |
| RF-048.26 | A lista deve exibir as colunas: Agência, Período, Comissão Líquida (R$), Data da Solicitação, Status                                            |
| RF-048.27 | O sistema deve disponibilizar filtros por: Agência (busca por nome), Status (Repasse Solicitado, Em Contestação, Repasse Pago) e Período (mês/ano) |
| RF-048.28 | O Administrador deve poder clicar em uma solicitação para visualizar os detalhes: período, comissão líquida, dados bancários da Agência, observação enviada e o detalhamento por transação com totalizador de conferência (RF-048.10A/10B) |
| RF-048.29 | O sistema deve exibir botão "Autorizar Repasse" para solicitações com status "Repasse Solicitado"                                                |
| RF-048.30 | Ao autorizar o repasse, o sistema deve exibir modal solicitando: data do repasse e campo opcional para upload de comprovante                      |
| RF-048.31 | Ao confirmar a autorização, o sistema deve alterar o status para "Repasse Pago", enviar notificação à Agência **e enviar notificação informativa a cada Agente vinculado**, comunicando que o repasse do período foi processado |
| RF-048.32 | O sistema deve exibir botão "Rejeitar" com campo obrigatório de motivo para solicitações pendentes                                               |
| RF-048.33 | O sistema deve exibir aba ou seção "Histórico de Repasses" com todos os repasses já realizados, filtráveis por Agência e Período                 |
| RF-048.33A | O sistema deve exibir, na visão do Administrador, lista consolidada de Reportes de Divergência (RF-048.24A) enviados por Agentes, com colunas: Agente, Agência, Período, Transação, Status, Data do Reporte, filtrável por Status e Período |

Fechamento de Período (Administrador)

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.34 | O sistema deve disponibilizar ao Administrador botão "Fechar Período" para encerrar manualmente o período de apuração atual                      |
| RF-048.35 | Ao acionar o fechamento, o sistema deve exibir modal de confirmação informando o período a ser fechado e o total de comissões consolidadas        |
| RF-048.36 | Após o fechamento, o sistema deve consolidar todas as comissões do período, aplicar as deduções de cancelamentos/reembolsos e alterar o status para "Fechado" |
| RF-048.37 | Após o fechamento do período, novas vendas devem ser contabilizadas automaticamente no próximo período de apuração                               |

Ajuste Avulso em Período com Repasse Pago (Administrador)

| ID        | Requisito                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.38 | Para períodos com status "Repasse Pago", o sistema **não deve permitir** reabertura ou alteração retroativa direta do período já liquidado (não há botão "Reabrir Período" ou "Estornar Fechamento") |
| RF-048.39 | O sistema deve disponibilizar ao Administrador a ação "Lançamento Avulso de Crédito/Débito", aplicável ao período de apuração **subsequente em aberto**, para corrigir erros identificados em períodos já pagos |
| RF-048.40 | O modal de Lançamento Avulso deve exigir: Agência (ou Agente, quando aplicável) de destino, tipo (Crédito ou Débito), valor, período de referência da correção (período pago original) e motivo/justificativa obrigatória |
| RF-048.41 | Lançamentos avulsos devem ser exibidos de forma destacada no detalhamento do período em que forem aplicados, com referência ao período original que motivou a correção |
| RF-048.42 | Sistema notifica a Agência; se o campo Agente estiver preenchido no lançamento (RF-048.40), o Agente também é notificado obrigatoriamente |

Colunas Adicionais — Detalhamento por Transação

| Coluna                       | Conteúdo                                  | Opcional/Expansível | Observação                                                  |
|-------------------------------|--------------------------------------------|----------------------|---------------------------------------------------------------|
| Ingresso                      | Tipo/nome do ingresso vendido              | ✅ (RF-048.10A)       | Exibido na visão expandida por transação                     |
| Valor da Venda                | Valor monetário da venda individual        | ✅ (RF-048.10A)       | Base de cálculo da comissão                                   |
| % Comissão Configurada        | Percentual configurado em RF-010           | ✅ (RF-048.10A)       | Usado para detectar divergência (RF-048.10C)                 |
| Valor da Comissão Calculada   | Valor monetário da comissão da transação   | ✅ (RF-048.10A)       | Somado no totalizador de conferência (RF-048.10B)             |

Regras de Negócio

| ID        | Regra                                                                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-048.01 | A comissão é calculada sobre o **valor líquido da venda** após aplicação de descontos de cupom; o valor bruto não deve ser utilizado como base    |
| RN-048.02 | A taxa de comissão é definida em RF-010 (Configurações Comerciais) e pode variar por tipo de pagamento (Cartão de Crédito, PIX, etc.)            |
| RN-048.03 | O período de apuração padrão é **mensal**; o Administrador pode acionar o fechamento manual a qualquer momento                                   |
| RN-048.04 | Cancelamentos e reembolsos **dentro do período em aberto** deduzem diretamente a comissão do período corrente antes do fechamento                |
| RN-048.05 | Cancelamentos e reembolsos **após o fechamento do período** geram compensação (dedução) no próximo período de apuração, independentemente de o repasse do período fechado já ter sido pago ou não |
| RN-048.06 | A Agência **não pode** solicitar repasse de um período ainda com status "Aguardando Fechamento"; o período deve estar com status "Fechado"        |
| RN-048.07 | O repasse deve ser realizado exclusivamente para os dados bancários cadastrados pela Agência conforme RF-045 (Cadastro de Agências - Dados Bancários) |
| RN-048.08 | A contestação (Agência) ou o reporte de divergência (Agente) só é permitido enquanto o período estiver com status "Fechado" ou "Repasse Solicitado"; após o status "Repasse Pago", nenhuma alteração retroativa direta é possível — correções seguem RN-048.14 |
| RN-048.09 | O perfil Agente **não pode** solicitar repasse diretamente; o repasse é sempre realizado para a Agência à qual o Agente está vinculado **no momento da venda que originou a comissão** (vide RN-048.13). Caso o Agente tenha sido transferido para outra agência, eventuais comissões pendentes de períodos anteriores à transferência continuam sendo repassadas à agência de origem, que é responsável pelo acerto financeiro com o Agente conforme acordo comercial entre as partes |
| RN-048.10 | Ao fechar o período, o sistema deve **bloquear alterações retroativas** nas comissões já consolidadas                                            |
| RN-048.11 | O Administrador deve resolver contestações (Agência) ou reportes de divergência (Agente) com uma das resoluções: Aprovada Total, Aprovada Parcialmente (informando novo valor) ou Rejeitada (com motivo) |
| RN-048.12 | Notificações automáticas devem ser enviadas: à Agência ao ter repasse autorizado ou rejeitado; **a cada Agente vinculado, de forma informativa, quando o repasse do período é pago**; ao Administrador ao receber nova solicitação, contestação ou reporte de divergência de Agente |
| RN-048.13 | **Imutabilidade do Vínculo Financeiro:** a comissão gerada por uma venda pertence irrevogavelmente à Agência à qual o Agente estava vinculado no exato momento da emissão do bilhete/confirmação da venda. A migração posterior do Agente para outra agência (RF-046) não transfere o direito de recebimento das comissões retroativas para a nova agência. O repasse do período fechado será sempre enviado para a agência detentora do vínculo na data da venda, mesmo que o vínculo já tenha sido desfeito no momento do repasse |
| RN-048.14 | Erros identificados em períodos com status "Repasse Pago" **não podem sofrer alteração retroativa** no período original. A correção deve ser aplicada pelo Administrador exclusivamente por meio de um Lançamento Avulso de Crédito ou Débito (RF-048.39) na folha de apuração do período de apuração subsequente (em aberto) |
| RN-048.15 | O Agente pode reportar divergência de comissão diretamente ao Administrador (RF-048.24A), independentemente de a Agência também poder contestar o mesmo período; ambos os canais (contestação da Agência e reporte do Agente) coexistem e são tratados de forma independente, podendo o Administrador correlacioná-los durante a análise |

Critérios de Aceitação

| ID        | Critério                                                                                     | Resultado Esperado                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| CA-048.01 | Agência acessa o painel de comissões com período em aberto                                   | Resumo exibe Comissão Bruta, Deduções e Comissão Líquida corretamente calculados                                        |
| CA-048.02 | Agência visualiza histórico de períodos fechados                                             | Tabela exibe todos os períodos com colunas corretas e badge de status com cor correspondente                            |
| CA-048.03 | Agência clica em um período da tabela                                                        | Detalhamento expande exibindo breakdown por atração e por agente com valores corretos                                   |
| CA-048.03A | Agência expande o detalhamento por transação (RF-048.10A) em período "Aguardando Fechamento" com uma transação cuja comissão aplicada (10%) não corresponde ao percentual configurado (15%) | Linha da transação é sinalizada visualmente como divergente; totalizador de conferência reflete o valor efetivamente calculado, permitindo identificar a diferença antes do fechamento |
| CA-048.04 | Agência tenta solicitar repasse de período com status "Aguardando Fechamento"                | Botão "Solicitar Repasse" não aparece ou está desabilitado para o período                                               |
| CA-048.05 | Agência clica em "Solicitar Repasse" de período com status "Fechado"                         | Modal abre exibindo período, comissão líquida e dados bancários cadastrados                                             |
| CA-048.06 | Agência confirma a solicitação de repasse                                                    | Status do período muda para "Repasse Solicitado" e Administrador recebe notificação                                     |
| CA-048.07 | Agência clica em "Contestar" em período com status "Fechado"                                 | Formulário de contestação abre com lista de transações do período para seleção                                          |
| CA-048.08 | Agência envia contestação selecionando transações, motivo e valor esperado                   | Status muda para "Em Contestação", Administrador recebe notificação e histórico de contestação é registrado             |
| CA-048.09 | Agência tenta contestar período com status "Repasse Pago"                                    | Botão "Contestar" não está disponível; sistema exibe mensagem informando que o repasse já foi realizado e orienta sobre lançamento avulso (RF-048.39) |
| CA-048.10 | Agente acessa o painel de comissões                                                          | Painel exibe apenas comissões individuais do Agente, sem botões de "Solicitar Repasse" ou contestação completa da Agência, mas com botão "Reportar Divergência" disponível por transação |
| CA-048.10A | Agente identifica comissão recebida abaixo do percentual configurado para o ingresso vendido e clica em "Reportar Divergência" | Modal abre solicitando motivo/descrição e valor esperado (opcional); ao confirmar, divergência é registrada com status "Reportada" e Administrador e Agência são notificados |
| CA-048.11 | Administrador acessa tela de gestão de repasses                                              | Lista de solicitações pendentes exibe Agência, Período, Comissão Líquida, Data da Solicitação e Status                  |
| CA-048.12 | Administrador filtra solicitações por Agência e Status                                       | Lista atualiza exibindo apenas os registros correspondentes aos filtros aplicados                                       |
| CA-048.13 | Administrador autoriza repasse e informa data e comprovante                                  | Status muda para "Repasse Pago", comprovante é armazenado, Agência recebe notificação **e cada Agente vinculado ao período recebe notificação informativa do repasse** |
| CA-048.14 | Administrador rejeita solicitação informando motivo                                          | Status retorna para "Fechado", Agência recebe notificação com o motivo da rejeição                                      |
| CA-048.15 | Administrador aciona fechamento do período mensal                                            | Modal de confirmação é exibido; ao confirmar, todas as comissões são consolidadas e status muda para "Fechado"          |
| CA-048.16 | Venda cancelada dentro do período em aberto                                                  | Comissão da venda é deduzida do total do período corrente antes do fechamento                                           |
| CA-048.17 | Venda cancelada após o fechamento do período (período ainda não pago)                        | Dedução é registrada no próximo período de apuração, não no período já fechado                                          |
| CA-048.17A | Venda cancelada após o período já estar com status "Repasse Pago"                            | Dedução/débito é registrada no próximo período de apuração em aberto (não há alteração retroativa no período pago)      |
| CA-048.18 | Administrador resolve contestação como "Aprovada Parcialmente" informando novo valor         | Comissão líquida do período é atualizada com o novo valor aprovado e Agência recebe notificação com resultado           |
| CA-048.19 | Administrador tenta reabrir ou alterar diretamente um período com status "Repasse Pago"      | Sistema não oferece nenhuma ação de reabertura/estorno de fechamento; única via de correção é o Lançamento Avulso (RF-048.39) |
| CA-048.20 | Administrador identifica erro em período já pago e aplica Lançamento Avulso de Débito        | Lançamento é aplicado ao período subsequente em aberto, exibido de forma destacada com referência ao período original; Agência (e Agente, se aplicável) são notificados |
| CA-048.21 | Agente é transferido de uma agência para outra (RF-046) e existem comissões de vendas anteriores à transferência ainda não repassadas | O repasse dessas comissões é direcionado à agência de origem (detentora do vínculo na data da venda), mesmo após a transferência |

Protótipo/Wireframe

Figura - WF-052 - Comissionamento - Agência.png (a definir)
