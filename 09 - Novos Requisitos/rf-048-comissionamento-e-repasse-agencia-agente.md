### 3.48 Comissionamento e Repasse - Agência e Agente

**ID:** RF-048

Módulo: Gestão de Agências > Financeiro / Comissionamento

Perfis com Acesso: Administrador, Agência, Agente

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir o gerenciamento completo do ciclo de comissionamento e repasse financeiro para Agências e Agentes. Isso inclui: visualização de comissões acumuladas por período, fechamento mensal de períodos pelo Administrador, solicitação e autorização de repasses, contestação de valores e notificações automáticas a todos os perfis envolvidos.

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

Modal de Solicitação de Repasse (Agência)

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.11 | Ao clicar em "Solicitar Repasse", o sistema deve abrir modal exibindo: período de referência, valor da comissão líquida e dados bancários cadastrados |
| RF-048.12 | O modal deve exibir link "Atualizar dados bancários" caso a Agência deseje alterar as informações antes de confirmar (redireciona para RF-045)    |
| RF-048.13 | O modal deve exibir campo de texto opcional para observação da Agência                                                                           |
| RF-048.14 | O modal deve exibir botão "Confirmar Solicitação" e botão "Cancelar"                                                                             |
| RF-048.15 | Ao confirmar, o sistema deve alterar o status do período para "Repasse Solicitado" e enviar notificação ao Administrador                         |

Contestação de Comissão (Agência)

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.16 | Ao clicar em "Contestar", o sistema deve abrir formulário de contestação com a lista de transações (pedidos) do período                          |
| RF-048.17 | O formulário deve permitir selecionar uma ou mais transações a serem contestadas                                                                  |
| RF-048.18 | O formulário deve exibir campo obrigatório "Motivo da Contestação" e campo "Valor Esperado"                                                      |
| RF-048.19 | Ao enviar a contestação, o sistema deve alterar o status do período para "Em Contestação" e enviar notificação ao Administrador                  |
| RF-048.20 | O sistema deve registrar histórico de contestações com data, motivo e status de resolução (Aprovada Total / Aprovada Parcialmente / Rejeitada)   |

Painel de Comissões — Visão do Agente

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.21 | O sistema deve exibir, para o perfil Agente, painel simplificado com resumo das comissões individuais acumuladas no período atual                |
| RF-048.22 | O sistema deve exibir tabela de vendas do Agente com comissão por transação: Data, Atração, Ingresso, Valor da Venda, % Comissão, Valor Comissão |
| RF-048.23 | O sistema deve exibir tabela de histórico de períodos fechados com: Período, Vendas (R$), Comissão Bruta, Deduções, Comissão Líquida e Status    |
| RF-048.24 | O perfil Agente **não** deve ter acesso ao botão "Solicitar Repasse" nem ao formulário de contestação                                            |

Visão do Administrador — Gestão de Repasses

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.25 | O sistema deve exibir, para o Administrador, tela de gestão de repasses com lista de solicitações pendentes                                      |
| RF-048.26 | A lista deve exibir as colunas: Agência, Período, Comissão Líquida (R$), Data da Solicitação, Status                                            |
| RF-048.27 | O sistema deve disponibilizar filtros por: Agência (busca por nome), Status (Repasse Solicitado, Em Contestação, Repasse Pago) e Período (mês/ano) |
| RF-048.28 | O Administrador deve poder clicar em uma solicitação para visualizar os detalhes: período, comissão líquida, dados bancários da Agência e observação enviada |
| RF-048.29 | O sistema deve exibir botão "Autorizar Repasse" para solicitações com status "Repasse Solicitado"                                                |
| RF-048.30 | Ao autorizar o repasse, o sistema deve exibir modal solicitando: data do repasse e campo opcional para upload de comprovante                      |
| RF-048.31 | Ao confirmar a autorização, o sistema deve alterar o status para "Repasse Pago" e enviar notificação à Agência                                   |
| RF-048.32 | O sistema deve exibir botão "Rejeitar" com campo obrigatório de motivo para solicitações pendentes                                               |
| RF-048.33 | O sistema deve exibir aba ou seção "Histórico de Repasses" com todos os repasses já realizados, filtráveis por Agência e Período                 |

Fechamento de Período (Administrador)

| ID        | Requisito                                                                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-048.34 | O sistema deve disponibilizar ao Administrador botão "Fechar Período" para encerrar manualmente o período de apuração atual                      |
| RF-048.35 | Ao acionar o fechamento, o sistema deve exibir modal de confirmação informando o período a ser fechado e o total de comissões consolidadas        |
| RF-048.36 | Após o fechamento, o sistema deve consolidar todas as comissões do período, aplicar as deduções de cancelamentos/reembolsos e alterar o status para "Fechado" |
| RF-048.37 | Após o fechamento do período, novas vendas devem ser contabilizadas automaticamente no próximo período de apuração                               |

Regras de Negócio

| ID        | Regra                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-048.01 | A comissão é calculada sobre o **valor líquido da venda** após aplicação de descontos de cupom; o valor bruto não deve ser utilizado como base    |
| RN-048.02 | A taxa de comissão é definida em RF-010 (Configurações Comerciais) e pode variar por tipo de pagamento (Cartão de Crédito, PIX, etc.)            |
| RN-048.03 | O período de apuração padrão é **mensal**; o Administrador pode acionar o fechamento manual a qualquer momento                                   |
| RN-048.04 | Cancelamentos e reembolsos **dentro do período em aberto** deduzem diretamente a comissão do período corrente antes do fechamento                |
| RN-048.05 | Cancelamentos e reembolsos **após o fechamento do período** geram compensação (dedução) no próximo período de apuração                           |
| RN-048.06 | A Agência **não pode** solicitar repasse de um período ainda com status "Aguardando Fechamento"; o período deve estar com status "Fechado"        |
| RN-048.07 | O repasse deve ser realizado exclusivamente para os dados bancários cadastrados pela Agência conforme RF-045 (Cadastro de Agências - Dados Bancários) |
| RN-048.08 | A contestação só é permitida enquanto o período estiver com status "Fechado" ou "Repasse Solicitado"; após o status "Repasse Pago" não é possível contestar |
| RN-048.09 | O perfil Agente **não pode** solicitar repasse diretamente; o repasse é sempre realizado para a Agência à qual o Agente está vinculado            |
| RN-048.10 | Ao fechar o período, o sistema deve **bloquear alterações retroativas** nas comissões já consolidadas                                            |
| RN-048.11 | O Administrador deve resolver contestações com uma das resoluções: Aprovada Total, Aprovada Parcialmente (informando novo valor) ou Rejeitada (com motivo) |
| RN-048.12 | Notificações automáticas devem ser enviadas: à Agência ao ter repasse autorizado ou rejeitado; ao Administrador ao receber nova solicitação ou contestação |

Critérios de Aceitação

| ID        | Critério                                                                                     | Resultado Esperado                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| CA-048.01 | Agência acessa o painel de comissões com período em aberto                                   | Resumo exibe Comissão Bruta, Deduções e Comissão Líquida corretamente calculados                                        |
| CA-048.02 | Agência visualiza histórico de períodos fechados                                             | Tabela exibe todos os períodos com colunas corretas e badge de status com cor correspondente                            |
| CA-048.03 | Agência clica em um período da tabela                                                        | Detalhamento expande exibindo breakdown por atração e por agente com valores corretos                                   |
| CA-048.04 | Agência tenta solicitar repasse de período com status "Aguardando Fechamento"                | Botão "Solicitar Repasse" não aparece ou está desabilitado para o período                                               |
| CA-048.05 | Agência clica em "Solicitar Repasse" de período com status "Fechado"                         | Modal abre exibindo período, comissão líquida e dados bancários cadastrados                                             |
| CA-048.06 | Agência confirma a solicitação de repasse                                                    | Status do período muda para "Repasse Solicitado" e Administrador recebe notificação                                     |
| CA-048.07 | Agência clica em "Contestar" em período com status "Fechado"                                 | Formulário de contestação abre com lista de transações do período para seleção                                          |
| CA-048.08 | Agência envia contestação selecionando transações, motivo e valor esperado                   | Status muda para "Em Contestação", Administrador recebe notificação e histórico de contestação é registrado             |
| CA-048.09 | Agência tenta contestar período com status "Repasse Pago"                                    | Botão "Contestar" não está disponível; sistema exibe mensagem informando que o repasse já foi realizado                 |
| CA-048.10 | Agente acessa o painel de comissões                                                          | Painel exibe apenas comissões individuais do Agente, sem botões de solicitação de repasse ou contestação                |
| CA-048.11 | Administrador acessa tela de gestão de repasses                                              | Lista de solicitações pendentes exibe Agência, Período, Comissão Líquida, Data da Solicitação e Status                  |
| CA-048.12 | Administrador filtra solicitações por Agência e Status                                       | Lista atualiza exibindo apenas os registros correspondentes aos filtros aplicados                                       |
| CA-048.13 | Administrador autoriza repasse e informa data e comprovante                                  | Status muda para "Repasse Pago", comprovante é armazenado e Agência recebe notificação                                  |
| CA-048.14 | Administrador rejeita solicitação informando motivo                                          | Status retorna para "Fechado", Agência recebe notificação com o motivo da rejeição                                      |
| CA-048.15 | Administrador aciona fechamento do período mensal                                            | Modal de confirmação é exibido; ao confirmar, todas as comissões são consolidadas e status muda para "Fechado"          |
| CA-048.16 | Venda cancelada dentro do período em aberto                                                  | Comissão da venda é deduzida do total do período corrente antes do fechamento                                           |
| CA-048.17 | Venda cancelada após o fechamento do período                                                 | Dedução é registrada no próximo período de apuração, não no período já fechado                                          |
| CA-048.18 | Administrador resolve contestação como "Aprovada Parcialmente" informando novo valor         | Comissão líquida do período é atualizada com o novo valor aprovado e Agência recebe notificação com resultado           |

Protótipo/Wireframe

Figura - WF-052 - Comissionamento - Agência.png (a definir)
