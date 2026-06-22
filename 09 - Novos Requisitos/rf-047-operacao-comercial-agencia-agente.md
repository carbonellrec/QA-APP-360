### 3.47 Operação Comercial - Agência e Agente

**ID:** RF-047

Módulo: Gestão de Agências > Operação Comercial

Perfis com Acesso: Agência (suas vendas + vendas dos seus agentes); Agente (apenas suas vendas); Administrador (todas as vendas)

**Prioridade:** Alta (Essencial)

**Descrição:** Painel de operação comercial para os perfis Agência e Agente, exibindo KPIs de vendas, histórico de transações, gerenciamento de cupons emitidos e opção de cancelamento de vendas recentes. O Administrador acessa visão global de todas as agências/agentes.

Requisitos Detalhados

Estrutura Geral do Painel

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.01 | O sistema deve exibir o título "Operação Comercial" no topo da tela                                                         |
| RF-047.02 | O sistema deve exibir filtros de período: Hoje, Esta semana, Este mês, Período personalizado                                |
| RF-047.03 | O período personalizado deve permitir seleção de data inicial e data final via seletor de datas                             |
| RF-047.04 | O sistema deve exibir filtro por Atração (select com as atrações disponíveis)                                               |
| RF-047.05 | O sistema deve exibir filtro por Agente apenas quando o perfil logado for Agência                                           |
| RF-047.06 | O sistema deve exibir filtro por Agência apenas quando o perfil logado for Administrador                                    |
| RF-047.07 | O sistema deve exibir botão "Exportar" com opções CSV e PDF                                                                 |
| RF-047.08 | Todos os filtros devem atualizar os KPIs e a tabela de transações ao serem aplicados                                        |

Cards de KPIs

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.09 | O sistema deve exibir card "Total de Vendas (R$)" calculado conforme os filtros aplicados                                   |
| RF-047.10 | O sistema deve exibir card "Qtd de Ingressos Vendidos" calculado conforme os filtros aplicados                              |
| RF-047.11 | O sistema deve exibir card "Comissão Acumulada no Período" calculado conforme os filtros aplicados                          |
| RF-047.12 | O sistema deve exibir card "Cupons Emitidos / Utilizados" calculado conforme os filtros aplicados                           |

Tabela de Transações

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.13 | O sistema deve exibir tabela de transações com as colunas: ID Pedido, Data/Hora, Turista (nome + e-mail), Atração, Qtd Ingressos, Valor Total (R$), Cupom Utilizado, Comissão (R$ e %), Status |
| RF-047.14 | Todas as colunas da tabela devem ser ordenáveis (ASC/DESC)                                                                  |
| RF-047.15 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100                              |
| RF-047.16 | Ao clicar em uma linha da tabela, o sistema deve abrir modal com detalhes completos da transação                            |
| RF-047.17 | A coluna Status deve exibir badge visual com os valores: Confirmado, Cancelado, Reembolsado                                 |

Modal de Detalhes da Transação

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.18 | O modal de detalhes deve exibir: ID Pedido, Data/Hora, nome do Turista, e-mail e telefone                                  |
| RF-047.19 | O modal deve exibir: Atração, Tipo de Ingresso, Qtd, Valor Total, Desconto (cupom aplicado)                                 |
| RF-047.20 | O modal deve exibir: Forma de Pagamento, Comissão (R$ e %), Status atual, QR Code do ingresso                              |
| RF-047.21 | O modal deve exibir Histórico de Status com data/hora de cada alteração de status do pedido                                 |
| RF-047.22 | O modal deve exibir botão "Cancelar Venda" quando o pedido estiver elegível para cancelamento                               |

Ação: Cancelar Venda

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.23 | O botão "Cancelar Venda" deve ser exibido apenas para pedidos com status "Confirmado" e com até 24h após a venda            |
| RF-047.24 | Ao clicar em "Cancelar Venda", o sistema deve exibir modal de confirmação com campo de motivo obrigatório                   |
| RF-047.25 | Ao confirmar o cancelamento, o sistema deve invalidar o ingresso, estornar a comissão e enviar e-mail ao turista com o motivo |
| RF-047.26 | Após 24h da venda, o botão "Cancelar Venda" não deve ser exibido; o cancelamento deve ser encaminhado via RF-049            |

Cupons Emitidos pela Agência

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.27 | O sistema deve exibir seção com lista de cupons criados/atribuídos à agência                                                |
| RF-047.28 | A lista de cupons deve exibir colunas: Código, Desconto (%), Qtd Disponível, Qtd Utilizada, Validade, Status               |
| RF-047.29 | O sistema deve exibir botão "Gerar novo cupom" que abre modal consistente com o fluxo definido em RF-018                   |

Exportação

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.30 | O sistema deve exportar as transações exibidas na tabela (conforme filtros aplicados) em formato CSV                        |
| RF-047.31 | O sistema deve exportar as transações exibidas na tabela (conforme filtros aplicados) em formato PDF                        |

Visão do Administrador

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.32 | O Administrador deve ter acesso às mesmas funcionalidades do painel com filtros adicionais por Agência e por Agente         |
| RF-047.33 | A visão do Administrador deve consolidar todas as transações de todas as agências e agentes                                 |

Colunas da Tabela de Transações

| Coluna            | Conteúdo                           | Ordenável | Observação                               |
|-------------------|------------------------------------|-----------|------------------------------------------|
| ID Pedido         | Identificador único do pedido      | ✅         | Ordenação padrão DESC                    |
| Data/Hora         | DD/MM/AAAA HH:MM:SS                | ✅         | Data e hora da venda                     |
| Turista           | Nome + e-mail                      | ✅         | Ordena por nome do turista               |
| Atração           | Nome da atração                    | ✅         | Atração vinculada ao ingresso            |
| Qtd Ingressos     | Número inteiro                     | ✅         | Quantidade de ingressos no pedido        |
| Valor Total (R$)  | Valor monetário formatado          | ✅         | Valor bruto do pedido                    |
| Cupom Utilizado   | Código do cupom ou "-"             | ✅         | "-" quando nenhum cupom foi aplicado     |
| Comissão (R$ e %) | Valor e percentual da comissão     | ✅         | Calculado conforme RF-010                |
| Status            | Badge: Confirmado/Cancelado/Reembolsado | ✅   | Status atual do pedido                   |

Disponibilidade de Filtros por Perfil

| Filtro        | Agente | Agência | Administrador |
|---------------|--------|---------|---------------|
| Período       | ✅      | ✅       | ✅             |
| Atração       | ✅      | ✅       | ✅             |
| Por Agente    | ❌      | ✅       | ✅             |
| Por Agência   | ❌      | ❌       | ✅             |

Regras de Negócio

| ID        | Regra                                                                                                                       |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RN-047.01 | O perfil Agente visualiza **apenas suas próprias vendas**, sem acesso às vendas de outros agentes ou da agência            |
| RN-047.02 | O perfil Agência visualiza suas próprias vendas **e** as vendas de todos os agentes vinculados a ela                       |
| RN-047.03 | O perfil Administrador visualiza **todas as transações** de todas as agências e agentes do sistema                         |
| RN-047.04 | O cancelamento de venda está disponível **somente até 24 horas** após o momento da venda                                   |
| RN-047.05 | Ao cancelar uma venda, o ingresso é invalidado imediatamente e a comissão do período é estornada                           |
| RN-047.06 | Após 24h, o cancelamento só pode ser processado via fila de reembolsos do Administrador (RF-049)                           |
| RN-047.07 | Os KPIs exibidos sempre refletem o **período e os filtros selecionados** pelo usuário                                      |
| RN-047.08 | A comissão é calculada conforme as taxas configuradas no módulo de Configurações Comerciais (RF-010)                       |
| RN-047.09 | Vendas com status "Reembolsado" (processadas via RF-049) deduzem as comissões do período exibido                           |
| RN-047.10 | Os cupons da agência possuem validade e quantidade máxima de uso, configurados conforme RF-018                             |
| RN-047.11 | A exportação gera arquivo com **todos os registros** da tabela conforme os filtros aplicados, sem limite de linhas          |

Critérios de Aceitação

| ID        | Critério                                                           | Resultado Esperado                                                                                         |
|-----------|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| CA-047.01 | Acessar o painel como Agente                                       | Tabela exibe apenas as vendas do agente logado; filtro por Agente e Agência não são exibidos               |
| CA-047.02 | Acessar o painel como Agência                                      | Tabela exibe vendas da agência e de todos os seus agentes; filtro por Agente está disponível               |
| CA-047.03 | Acessar o painel como Administrador                                | Tabela exibe todas as transações do sistema; filtros por Agência e por Agente estão disponíveis            |
| CA-047.04 | Aplicar filtro de período "Este mês"                               | KPIs e tabela atualizam exibindo apenas transações do mês corrente                                         |
| CA-047.05 | Aplicar filtro por Atração específica                              | KPIs e tabela atualizam exibindo apenas transações daquela atração                                         |
| CA-047.06 | Aplicar filtro por Agente (perfil Agência)                         | KPIs e tabela atualizam exibindo apenas transações do agente selecionado                                   |
| CA-047.07 | Alterar período e verificar KPIs                                   | Cards de Total de Vendas, Qtd de Ingressos, Comissão e Cupons refletem exatamente o período selecionado    |
| CA-047.08 | Clicar em uma linha da tabela                                      | Modal de detalhes abre exibindo todas as informações do pedido, incluindo QR Code e histórico de status    |
| CA-047.09 | Cancelar venda com menos de 24h (status Confirmado)                | Modal de confirmação é exibido; ao confirmar: ingresso invalidado, comissão estornada, e-mail enviado ao turista |
| CA-047.10 | Tentar cancelar venda com mais de 24h                              | Botão "Cancelar Venda" não é exibido no modal de detalhes                                                  |
| CA-047.11 | Clicar em "Exportar" e selecionar CSV                              | Arquivo CSV é gerado e baixado com todos os registros conforme filtros aplicados                           |
| CA-047.12 | Clicar em "Exportar" e selecionar PDF                              | Arquivo PDF é gerado e baixado com todos os registros conforme filtros aplicados                           |
| CA-047.13 | Clicar em "Gerar novo cupom" na seção de Cupons                    | Modal de geração de cupom é exibido conforme fluxo de RF-018                                               |
| CA-047.14 | Verificar KPIs com venda de status "Reembolsado" no período        | Comissão acumulada deduz o valor referente ao pedido reembolsado                                           |
| CA-047.15 | Alterar paginação para 50 registros                                | Tabela exibe até 50 transações por página                                                                  |

Protótipo/Wireframe

Figura - WF-051 - Operação Comercial - Agência.png (a definir)
