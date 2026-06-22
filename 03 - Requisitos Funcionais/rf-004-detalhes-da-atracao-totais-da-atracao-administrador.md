### 3.4 Detalhes da Atração / Totais da Atração - Administrador

**ID:** RF-004

Módulo: Gestão de Atrações &gt; Totais da Atração

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve exibir uma tela de detalhes ao selecionar uma atração (via Dashboard ou menu Gestão de Atrações), apresentando:

- Informações da atração selecionada (nome, foto, localização)
- Menu lateral com submódulos de gestão da atração
- Cards com indicadores consolidados de vendas, ingressos e formas de pagamento
- Filtros de período para análise dos dados

Esta tela é o ponto central de gestão de cada atração, dando acesso a todos os submódulos relacionados.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-004.01 | O sistema deve exibir o nome da atração selecionada no cabeçalho da área de conteúdo       |
| RF-004.02 | O sistema deve exibir a foto/imagem da atração no painel lateral esquerdo                  |
| RF-004.03 | O sistema deve exibir a localização da atração (bairro - cidade) abaixo da foto            |
| RF-004.04 | O sistema deve exibir um menu lateral com os submódulos disponíveis para gestão da atração |
| RF-004.05 | O sistema deve destacar visualmente o submódulo ativo/selecionado no menu                  |
| RF-004.06 | O sistema deve manter o contexto da atração selecionada ao navegar entre submódulos        |
| RF-004.07 | O sistema deve disponibilizar link para retornar ao Dashboard no menu lateral              |

Filtros de Período

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-004.08 | O sistema deve exibir botões de filtro rápido: "Tudo", "Hoje", "7 Dias", "30 Dias"     |
| RF-004.09 | O sistema deve exibir opção "Período" para seleção de intervalo de datas personalizado |
| RF-004.10 | O sistema deve atualizar todos os cards ao alterar o filtro de período                 |
| RF-004.11 | O sistema deve manter o filtro selecionado ao navegar entre submódulos                 |
| RF-004.12 | O filtro padrão ao acessar a tela deve ser "30 Dias"                                   |

Cards de Indicadores (KPIs)

| ID        | Requisito                                                                                                                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------|
| RF-004.13 | O sistema deve exibir cards organizados em grid responsivo                                                                   |
| RF-004.14 | Cada card deve exibir: título, descrição, quantidade de ingressos, percentual de variação, e métricas específicas            |
| RF-004.15 | O percentual de variação deve comparar com o período anterior equivalente                                                    |
| RF-004.16 | O sistema deve exibir indicadores visuais de variação positiva (verde/seta para cima) ou negativa (vermelho/seta para baixo) |

Cards de Indicadores Obrigatórios

Card 1: Ingressos Vendidos

| Campo                   | Descrição                                             |
|-------------------------|-------------------------------------------------------|
| Título                  | Ingressos Vendidos                                    |
| Subtítulo               | Ingressos Vendidos no período                         |
| Quantidade de Ingressos | Total de ingressos vendidos (unidades)                |
| Variação %              | Comparativo com período anterior                      |
| Valor das Vendas        | Valor total em R$                                     |
| Ticket Médio            | Valor médio por ingresso (R$)                         |
| Indicador de Meta       | "Acima da meta" / "Abaixo da meta" (quando aplicável) |

Card 2: Ingressos Emitidos

| Campo                   | Descrição                        |
|-------------------------|----------------------------------|
| Título                  | Ingressos Emitidos               |
| Subtítulo               | Ingressos Emitidos no período    |
| Quantidade de Ingressos | Total de ingressos emitidos      |
| Variação %              | Comparativo com período anterior |
| Cortesias               | Quantidade de ingressos cortesia |
| Total                   | Soma de vendidos + cortesias     |

Card 3: Ingressos Reservados

| Campo                   | Descrição                        |
|-------------------------|----------------------------------|
| Título                  | Ingressos Reservados             |
| Subtítulo               | Ingressos Reservados no período  |
| Quantidade de Ingressos | Total de ingressos em reserva    |
| Variação %              | Comparativo com período anterior |
| Quantidade              | Valor total reservado (R$)       |
| Total                   | Valor unitário médio (R$)        |

Card 4: Ingressos Validação

| Campo                   | Descrição                                      |
|-------------------------|------------------------------------------------|
| Título                  | Ingressos Validação                            |
| Subtítulo               | Ingressos Validados no período                 |
| Quantidade de Ingressos | Total de ingressos processados para validação  |
| Variação %              | Comparativo com período anterior               |
| Validados               | Quantidade efetivamente validados (utilizados) |
| Pendentes               | Quantidade ainda não validados                 |

Cards de Vendas por Forma de Pagamento

O sistema deve exibir um card para cada forma de pagamento disponível:

| Card    | Título                           | Subtítulo                           |
|---------|----------------------------------|-------------------------------------|
| Card 5  | Vendas no Dinheiro               | Vendas em dinheiro no período       |
| Card 6  | Vendas no C. Débito              | Vendas no cartão débito no período  |
| Card 7  | Vendas no C. Crédito             | Vendas no cartão crédito no período |
| Card 8  | Vendas no C. Crédito Parcelado   | Vendas no cartão crédito no período |
| Card 9  | Vendas no PIX                    | Vendas no PIX no período            |
| Card 10 | Vendas por depósito, TED, etc... | Vendas por depósito no período      |

Estrutura de cada card de pagamento:

| Campo                   | Descrição                                            |
|-------------------------|------------------------------------------------------|
| Quantidade de Ingressos | Total de ingressos vendidos nesta forma de pagamento |
| Variação %              | Comparativo com período anterior                     |
| Unidades Vendidas       | Label descritivo                                     |
| Quantidade              | Número de transações                                 |
| Total                   | Valor total em R$                                    |

Menu Lateral - Submódulos

|   Ordem | Submódulo          | Observação                          |
|---------|--------------------|-------------------------------------|
|       1 | Dashboard          | Retorna ao Dashboard geral          |
|       2 | Totais da Atração  | Tela atual (selecionada por padrão) |
|       3 | Categorias         | Gestão de categorias de ingressos   |
|       4 | Pesquisar Ingresso | Busca de ingressos vendidos         |
|       5 | Gestão de Cupons   | Criação e gestão de cupons          |
|       6 | Gráficos Analytics | Visualização gráfica de métricas    |
|       7 | Editar da Atração  | Edição de dados cadastrais          |
|       8 | Agências e Agentes | Vinculação de canais de vendas      |
|       9 | Usuários           | Gestão de usuários da atração       |
|      10 | Gestão Financeira  | Submenu com opções financeiras      |
|      11 | Validar Ingressos  | Interface de validação QR Code      |

Nota: O submódulo "Gestão Financeira" é um menu expansível que contém os seguintes submenus: Relatórios da Atração (Vendas, Abandono de Carrinho, Ingresso Detalhado, Categorias, Cortesias Emitidas, Validação, Comissões, Venda por Pagamentos, Borderô Resumido), Negociação Financeira (Informações Financeiras, Condições Comerciais) e Resumo das Despesas.

Regras de Negócio

| ID        | Regra                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------|
| RN-004.01 | Ao acessar os detalhes de uma atração, o submódulo "Totais da Atração" deve ser exibido por padrão |
| RN-004.02 | O filtro de período considera a  **data de venda**  do ingresso                                    |
| RN-004.03 | O percentual de variação compara o período selecionado com o período anterior de igual duração     |
| RN-004.04 | Se não houver dados no período anterior para comparação, exibir "N/A" no percentual                |
| RN-004.05 | Cards com valor zero devem ser exibidos normalmente (não ocultar)                                  |
| RN-004.06 | O Ticket Médio é calculado como: Valor das Vendas ÷ Quantidade de Ingressos Vendidos               |
| RN-004.07 | Ingressos cortesia não devem ser contabilizados no valor de vendas                                 |
| RN-004.08 | O indicador "Acima/Abaixo da meta" só é exibido se houver meta configurada para a atração          |
| RN-004.09 | Ao clicar em "Dashboard" no menu, o sistema retorna ao Dashboard geral (RF-003)                    |
| RN-004.10 | O submódulo "Gestão Financeira" deve expandir para exibir suas subopções                           |

Cálculos dos Indicadores

| Indicador         | Fórmula                                                                         |
|-------------------|---------------------------------------------------------------------------------|
| Ticket Médio      | Valor Total das Vendas ÷ Quantidade de Ingressos Vendidos                       |
| Variação %        | ((Valor Período Atual - Valor Período Anterior) ÷ Valor Período Anterior) × 100 |
| Total Emitidos    | Ingressos Vendidos + Cortesias                                                  |
| Taxa de Validação | (Ingressos Validados ÷ Ingressos Emitidos) × 100                                |

Critérios de Aceitação

| ID        | Critério                                      | Resultado Esperado                                              |
|-----------|-----------------------------------------------|-----------------------------------------------------------------|
| CA-004.01 | Acessar detalhes de uma atração via Dashboard | Tela exibe nome, foto, localização e cards com dados da atração |
| CA-004.02 | Visualizar submódulo "Totais da Atração"      | Submódulo destacado no menu e cards de indicadores exibidos     |
| CA-004.03 | Clicar no filtro "Hoje"                       | Todos os cards atualizam com dados do dia atual                 |
| CA-004.04 | Clicar no filtro "7 Dias"                     | Todos os cards atualizam com dados dos últimos 7 dias           |
| CA-004.05 | Clicar no filtro "30 Dias"                    | Todos os cards atualizam com dados dos últimos 30 dias          |
| CA-004.06 | Clicar no filtro "Período"                    | Exibe seletor de data inicial e data final                      |
| CA-004.07 | Selecionar período personalizado              | Cards atualizam com dados do intervalo selecionado              |
| CA-004.08 | Verificar card "Ingressos Vendidos"           | Exibe quantidade, valor, ticket médio e variação %              |
| CA-004.09 | Verificar card "Ingressos Emitidos"           | Exibe quantidade, cortesias e total                             |
| CA-004.10 | Verificar card "Ingressos Validação"          | Exibe quantidade, validados e pendentes                         |
| CA-004.11 | Verificar cards de formas de pagamento        | Cada forma exibe quantidade, número de transações e valor total |
| CA-004.12 | Variação positiva                             | Exibe percentual em verde com seta para cima                    |
| CA-004.13 | Variação negativa                             | Exibe percentual em vermelho com seta para baixo                |
| CA-004.14 | Clicar em "Categorias" no menu                | Sistema navega para submódulo mantendo contexto da atração      |
| CA-004.15 | Clicar em "Dashboard" no menu                 | Sistema retorna ao Dashboard geral                              |
| CA-004.16 | Clicar em "Sign Out"                          | Sistema realiza logout e redireciona para login                 |
| CA-004.17 | Atração sem vendas no período                 | Cards exibem valor "0" (não ocultar cards)                      |
| CA-004.18 | Atração sem período anterior para comparação  | Variação exibe "N/A"                                            |

Protótipo/Wireframe

Figura  - WF-003 - Detalhes da Atração/Totais da atração

### 3.5 Tela de Perfil
