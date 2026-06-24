### 3.47 Operação Comercial - Agência e Agente

**ID:** RF-047

Módulo: Gestão de Agências > Operação Comercial

Perfis com Acesso: Agência (suas vendas + vendas dos seus agentes); Agente (apenas suas vendas); Administrador (todas as vendas)

**Prioridade:** Alta (Essencial)

**Descrição:** Painel de operação comercial para os perfis Agência e Agente, exibindo KPIs de vendas, histórico de transações, gerenciamento de cupons emitidos e opção de cancelamento de vendas recentes. O Administrador acessa visão global de todas as agências/agentes. O cancelamento de venda dentro da janela de 24 horas está disponível para os três perfis (Agência, Agente e Administrador), respeitando o escopo de visibilidade de cada perfil (RN-047.01 a RN-047.03) e operando no nível do item de pedido (ingresso individual), permitindo cancelamento total ou parcial de pedidos com múltiplos ingressos.

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
| RF-047.08A | O sistema deve exibir filtro adicional por "Qtd de Vendas Canceladas/Reembolsadas", disponível para os perfis Agência e Administrador, permitindo identificar agentes ou agências com volume atípico de cancelamentos |

Cards de KPIs

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.09 | O sistema deve exibir card "Total de Vendas (R$)" calculado conforme os filtros aplicados                                   |
| RF-047.10 | O sistema deve exibir card "Qtd de Ingressos Vendidos" calculado conforme os filtros aplicados                              |
| RF-047.11 | O sistema deve exibir card "Comissão Acumulada no Período" calculado conforme os filtros aplicados                          |
| RF-047.12 | O sistema deve exibir card "Cupons Emitidos / Utilizados" calculado conforme os filtros aplicados                           |
| RF-047.12A | O sistema deve exibir card "Qtd de Vendas Canceladas/Reembolsadas" calculado conforme os filtros aplicados, visível para os perfis Agência e Administrador, permitindo identificar o volume de cancelamentos por agente vinculado |

Tabela de Transações

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.13 | O sistema deve exibir tabela de transações com as colunas: ID Pedido, Data/Hora, Turista (nome + e-mail), Atração, Qtd Ingressos, Valor Total (R$), Cupom Utilizado, Comissão (R$ e %), Status |
| RF-047.14 | Todas as colunas da tabela devem ser ordenáveis (ASC/DESC)                                                                  |
| RF-047.15 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100                              |
| RF-047.16 | Ao clicar em uma linha da tabela, o sistema deve abrir modal com detalhes completos da transação                            |
| RF-047.17 | A coluna Status deve exibir badge visual com os valores: Confirmado, Cancelado Total, Cancelado Parcial, Reembolsado        |

Modal de Detalhes da Transação

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.18 | O modal de detalhes deve exibir: ID Pedido, Data/Hora, nome do Turista, e-mail e telefone                                  |
| RF-047.19 | O modal deve exibir: Atração, Tipo de Ingresso, Qtd, Valor Total, Desconto (cupom aplicado)                                |
| RF-047.20 | O modal deve exibir: Forma de Pagamento, Comissão (R$ e %), Status atual, QR Code de cada ingresso individual do pedido     |
| RF-047.21 | O modal deve exibir Histórico de Status com data/hora de cada alteração de status do pedido ou de itens individuais do pedido |
| RF-047.22 | O modal deve exibir botão "Cancelar Venda" quando o pedido estiver elegível para cancelamento (total ou parcial)            |
| RF-047.22A | Quando o pedido contiver mais de um ingresso, o modal deve listar cada ingresso individualmente com checkbox de seleção, permitindo ao ator escolher um, vários ou todos os ingressos para cancelamento |
| RF-047.22B | Ingressos já cancelados ou reembolsados anteriormente devem ser exibidos com status correspondente e não podem ser selecionados novamente para cancelamento |

Ação: Cancelar Venda

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-047.23 | O botão "Cancelar Venda" deve ser exibido apenas para pedidos com ao menos um ingresso em status "Confirmado" e com até 24h após o momento da venda |
| RF-047.23A | O cancelamento de venda dentro da janela de 24h pode ser realizado pelos perfis **Agência** (suas vendas e dos agentes vinculados), **Agente** (apenas suas próprias vendas) e **Administrador** (qualquer venda do sistema), respeitando o escopo de visibilidade de cada perfil (RN-047.01 a RN-047.03) |
| RF-047.24 | Ao clicar em "Cancelar Venda", o sistema deve exibir modal de confirmação com a lista de ingressos selecionados e campo de motivo obrigatório |
| RF-047.25 | Ao confirmar o cancelamento, o sistema deve invalidar o(s) ingresso(s) selecionado(s) (gerando novo QR Code inválido/expirado para cada item cancelado), estornar a comissão proporcional aos itens cancelados e enviar e-mail ao turista informando quais itens foram cancelados e o motivo |
| RF-047.25A | Quando o cancelamento for parcial (alguns ingressos do pedido permanecem confirmados), o sistema deve manter o pedido com status "Cancelado Parcial", preservando os ingressos não cancelados válidos para uso, com QR Code inalterado |
| RF-047.25B | Quando o cancelamento abranger todos os ingressos do pedido, o sistema deve atualizar o status do pedido para "Cancelado Total" |
| RF-047.25C | O sistema deve processar o estorno ao turista (total ou proporcional aos itens cancelados) via gateway de pagamento, conforme a forma de pagamento original da transação |
| RF-047.25D | Quando o cancelamento for realizado pelo perfil Agência sobre a venda de um Agente vinculado, o sistema deve notificar o Agente (e-mail e/ou notificação interna) informando os itens cancelados e o motivo |
| RF-047.26 | Após 24h da venda, o botão "Cancelar Venda" não deve ser exibido; o cancelamento (total ou parcial) deve ser encaminhado via RF-049 |

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
| RF-047.34 | O Administrador e o perfil Agência devem ter acesso a um indicador (card e/ou coluna na tabela de agentes) de quantidade de cancelamentos/reembolsos realizados por cada agente vinculado, para fins de monitoramento |

Colunas da Tabela de Transações

| Coluna            | Conteúdo                           | Ordenável | Observação                               |
|-------------------|--------------------------------------|-----------|--------------------------------------------|
| ID Pedido         | Identificador único do pedido      | ✅         | Ordenação padrão DESC                    |
| Data/Hora         | DD/MM/AAAA HH:MM:SS                | ✅         | Data e hora da venda                     |
| Turista           | Nome + e-mail                      | ✅         | Ordena por nome do turista               |
| Atração           | Nome da atração                    | ✅         | Atração vinculada ao ingresso            |
| Qtd Ingressos     | Número inteiro                     | ✅         | Quantidade de ingressos no pedido (com indicação de quantos estão cancelados, se houver) |
| Valor Total (R$)  | Valor monetário formatado          | ✅         | Valor bruto do pedido                    |
| Cupom Utilizado   | Código do cupom ou "-"             | ✅         | "-" quando nenhum cupom foi aplicado     |
| Comissão (R$ e %) | Valor e percentual da comissão     | ✅         | Calculado conforme RF-010; reflete estorno proporcional em caso de cancelamento parcial |
| Status            | Badge: Confirmado/Cancelado Total/Cancelado Parcial/Reembolsado | ✅ | Status atual do pedido                   |

Disponibilidade de Filtros por Perfil

| Filtro                              | Agente | Agência | Administrador |
|--------------------------------------|--------|---------|----------------|
| Período                              | ✅      | ✅       | ✅              |
| Atração                              | ✅      | ✅       | ✅              |
| Por Agente                           | ❌      | ✅       | ✅              |
| Por Agência                          | ❌      | ❌       | ✅              |
| Qtd de Vendas Canceladas/Reembolsadas | ❌      | ✅       | ✅              |

Regras de Negócio

| ID        | Regra                                                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------------------------------------|
| RN-047.01 | O perfil Agente visualiza **apenas suas próprias vendas**, sem acesso às vendas de outros agentes ou da agência            |
| RN-047.02 | O perfil Agência visualiza suas próprias vendas **e** as vendas de todos os agentes vinculados a ela. Quando um agente é transferido de agência (RF-046), as vendas realizadas **antes** da transferência permanecem visíveis apenas para a agência de origem; a agência de destino visualiza apenas as vendas realizadas pelo agente **após** o vínculo ser estabelecido |
| RN-047.03 | O perfil Administrador visualiza **todas as transações** de todas as agências e agentes do sistema                         |
| RN-047.04 | O cancelamento de venda está disponível **somente até 24 horas** após o momento da venda, podendo ser executado pelos perfis **Agência**, **Agente** e **Administrador**, cada um restrito ao escopo de visibilidade definido em RN-047.01 a RN-047.03 (ex.: o Agente só pode cancelar suas próprias vendas; a Agência pode cancelar suas vendas e as de seus agentes; o Administrador pode cancelar qualquer venda) |
| RN-047.05 | Ao cancelar uma venda (total ou parcial), o(s) ingresso(s) selecionado(s) é(são) invalidado(s) imediatamente e a comissão do período é estornada de forma proporcional aos itens cancelados |
| RN-047.06 | Após 24h, o cancelamento (total ou parcial) só pode ser processado via fila de reembolsos do Administrador (RF-049)        |
| RN-047.07 | Os KPIs exibidos sempre refletem o **período e os filtros selecionados** pelo usuário                                      |
| RN-047.08 | A comissão é calculada conforme as taxas configuradas no módulo de Configurações Comerciais (RF-010)                       |
| RN-047.09 | Vendas com status "Reembolsado", "Cancelado Total" ou "Cancelado Parcial" (processadas via RF-047 ou RF-049) deduzem as comissões do período exibido na proporção dos itens afetados |
| RN-047.10 | Os cupons da agência possuem validade e quantidade máxima de uso, configurados conforme RF-018                             |
| RN-047.11 | A exportação gera arquivo com **todos os registros** da tabela conforme os filtros aplicados, sem limite de linhas          |
| RN-047.12 | Um pedido com múltiplos ingressos permite cancelamento **parcial**: o ator pode selecionar um subconjunto dos ingressos do pedido para cancelar, mantendo os demais itens válidos e com QR Code inalterado. O cancelamento parcial gera um novo pedido de referência (ou registro vinculado) refletindo somente os itens cancelados, para fins de rastreabilidade de estorno e comissão |
| RN-047.13 | Quando uma Agência cancela a venda de um Agente vinculado, o sistema deve notificar o Agente sobre o cancelamento, incluindo os itens afetados e o motivo informado |
| RN-047.14 | O turista deve conseguir visualizar, em sua área de pedidos no Portal Público, quais itens do pedido foram cancelados e o motivo do cancelamento informado pelo ator que executou a ação |
| RN-047.15 | Agências e o Administrador devem conseguir consultar a quantidade de cancelamentos/reembolsos realizados por cada agente, para fins de auditoria e monitoramento de qualidade operacional |

Critérios de Aceitação

| ID        | Critério                                                           | Resultado Esperado                                                                                         |
|-----------|-------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| CA-047.01 | Acessar o painel como Agente                                       | Tabela exibe apenas as vendas do agente logado; filtro por Agente e Agência não são exibidos               |
| CA-047.02 | Acessar o painel como Agência                                      | Tabela exibe vendas da agência e de todos os seus agentes; filtro por Agente está disponível               |
| CA-047.03 | Acessar o painel como Administrador                                | Tabela exibe todas as transações do sistema; filtros por Agência e por Agente estão disponíveis            |
| CA-047.04 | Aplicar filtro de período "Este mês"                               | KPIs e tabela atualizam exibindo apenas transações do mês corrente                                         |
| CA-047.05 | Aplicar filtro por Atração específica                              | KPIs e tabela atualizam exibindo apenas transações daquela atração                                         |
| CA-047.06 | Aplicar filtro por Agente (perfil Agência)                         | KPIs e tabela atualizam exibindo apenas transações do agente selecionado                                   |
| CA-047.07 | Alterar período e verificar KPIs                                   | Cards de Total de Vendas, Qtd de Ingressos, Comissão e Cupons refletem exatamente o período selecionado    |
| CA-047.08 | Clicar em uma linha da tabela                                      | Modal de detalhes abre exibindo todas as informações do pedido, incluindo QR Code de cada ingresso e histórico de status |
| CA-047.09 | Cancelar venda com menos de 24h (status Confirmado), selecionando todos os ingressos do pedido | Modal de confirmação é exibido; ao confirmar: todos os ingressos invalidados, comissão estornada integralmente, e-mail enviado ao turista, pedido marcado como "Cancelado Total" |
| CA-047.09A | Cancelar parcialmente um pedido com 2 ingressos, selecionando apenas 1 | Modal de confirmação exibe apenas o ingresso selecionado; ao confirmar: apenas esse ingresso é invalidado, comissão estornada proporcionalmente, pedido marcado como "Cancelado Parcial", o ingresso restante permanece válido com QR Code inalterado |
| CA-047.09B | Agência cancela venda de um Agente vinculado                       | Cancelamento processado conforme RN-047.04/05; sistema envia notificação ao Agente informando os itens cancelados e o motivo |
| CA-047.09C | Turista acessa sua área de pedidos após cancelamento parcial       | Sistema exibe quais itens do pedido foram cancelados e o motivo informado pelo ator responsável            |
| CA-047.10 | Tentar cancelar venda com mais de 24h                              | Botão "Cancelar Venda" não é exibido no modal de detalhes; orientação para encaminhar via RF-049           |
| CA-047.11 | Clicar em "Exportar" e selecionar CSV                              | Arquivo CSV é gerado e baixado com todos os registros conforme filtros aplicados                           |
| CA-047.12 | Clicar em "Exportar" e selecionar PDF                              | Arquivo PDF é gerado e baixado com todos os registros conforme filtros aplicados                           |
| CA-047.13 | Clicar em "Gerar novo cupom" na seção de Cupons                    | Modal de geração de cupom é exibido conforme fluxo de RF-018                                               |
| CA-047.14 | Verificar KPIs com venda de status "Reembolsado" ou "Cancelado" no período | Comissão acumulada deduz o valor referente ao(s) item(ns) cancelado(s)/reembolsado(s), proporcionalmente   |
| CA-047.15 | Alterar paginação para 50 registros                                | Tabela exibe até 50 transações por página                                                                  |
| CA-047.16 | Aplicar filtro "Qtd de Vendas Canceladas/Reembolsadas" (perfil Agência ou Administrador) | Lista/indicador exibe os agentes ou agências com maior volume de cancelamentos no período filtrado |
| CA-047.17 | Verificar histórico de vendas de um agente recém-transferido de agência | A agência de origem continua visualizando as vendas realizadas pelo agente antes da transferência; a agência de destino visualiza apenas as vendas realizadas após o novo vínculo |

Protótipo/Wireframe

Figura - WF-051 - Operação Comercial - Agência.png (a definir)
