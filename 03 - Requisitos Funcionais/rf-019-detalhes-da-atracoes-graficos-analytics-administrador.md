### 3.19 Detalhes da Atrações/Gráficos Analytics - Administrador

**ID:** RF-019

**Módulo** : Detalhes da Atração &gt; Gráficos Analytics

**Perfis** : Administrador, Parceiro Comercial

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve exibir um dashboard completo com gráficos e métricas do Google Analytics filtrados pela atração selecionada. Todos os dados são obtidos exclusivamente do Google Analytics, desde que o Parceiro Comercial tenha integrado sua conta do Google Analytics no cadastro (RF-005). Se não houver integração, o sistema deve exibir mensagem solicitando a integração. Os gráficos são interativos e todos são exibidos na mesma tela em formato de grid responsivo.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------|
| RF-019.01 | O sistema deve exibir título com o nome da atração selecionada (ex: "Atração Parque Jaime Lerner") |
| RF-019.02 | Todos os gráficos e métricas devem ser exibidos na mesma tela em formato de grid responsivo        |

Filtros de Período

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-019.03 | O sistema deve exibir botões de filtro rápido: "Tudo", "Hoje", "7 Dias", "30 Dias"     |
| RF-019.04 | O sistema deve exibir opção "Período" para seleção de intervalo de datas personalizado |
| RF-019.05 | O sistema deve atualizar todos os gráficos e métricas ao alterar o filtro de período   |
| RF-019.06 | O filtro padrão ao acessar a tela deve ser "30 Dias"                                   |
| RF-019.07 | O sistema deve manter o filtro selecionado ao recarregar a página                      |

Cards de KPIs (Key Performance Indicators)

| ID        | Requisito                                                                                                                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------|
| RF-019.08 | O sistema deve exibir card "Número de acessos" com valor numérico e indicador de variação percentual (+/-)                   |
| RF-019.09 | O sistema deve exibir card "Usuários únicos" com valor numérico e indicador de variação percentual (+/-)                     |
| RF-019.10 | O sistema deve exibir card "Quantidade vendida" com valor numérico e indicador de variação percentual (+/-)                  |
| RF-019.11 | O sistema deve exibir card "Tempo médio" com valor em formato "Xm Ys" (ex: 16m 44s) e indicador de variação percentual (+/-) |
| RF-019.12 | O sistema deve exibir card "Total vendido" com valor monetário (R$ 0,00) e indicador de variação percentual (+/-)            |
| RF-019.13 | O sistema deve exibir card "Ticket médio" com valor monetário (R$ 0,00) e indicador de variação percentual (+/-)             |
| RF-019.14 | O sistema deve exibir card "Conversão" com valor percentual (%) e indicador de variação percentual (+/-)                     |

Gráficos de Acessos e Visitas

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-019.16 | O sistema deve exibir gráfico de barras "Total de visitas" mostrando visitas por horário do dia (0h, 6h, 12h, 18h, 23h)     |
| RF-019.17 | O sistema deve exibir gráfico de barras "Total de ingressos" mostrando ingressos por horário do dia (0h, 6h, 12h, 18h, 23h) |
| RF-019.18 | O sistema deve exibir gráfico de barras "Acessos por horário" mostrando acessos por horário do dia                          |
| RF-019.19 | O sistema deve exibir gráfico de barras "Acessos e qtd de ingressos vendidos por data" mostrando dados por data             |

Gráficos de Estatísticas do Evento

| ID        | Requisito                                                                                                                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-019.20 | O sistema deve exibir gráfico de barras horizontais "Estatísticas do evento acessos" com as métricas: Engajamento do usuário, Acesso a página da atração, Adicionado ao carrinho, Primeiras Visitas |
| RF-019.21 | O gráfico deve exibir valores numéricos para cada métrica                                                                                                                                           |
| RF-019.22 | O gráfico deve ser interativo (hover para ver valores exatos, clicar para ver detalhes)                                                                                                             |

Gráficos Demográficos

| ID        | Requisito                                                                                                                       |
|-----------|---------------------------------------------------------------------------------------------------------------------------------|
| RF-019.23 | O sistema deve exibir gráfico de barras horizontais "Média de acessos por idade" com faixas etárias: 18-24, 24-34, 35-44, 45-54 |
| RF-019.24 | O sistema deve exibir gráfico de rosca (donut) "Acessos por gênero" com distribuição por gênero                                 |
| RF-019.25 | Os gráficos devem ser interativos (hover para ver valores, clicar para filtrar)                                                 |

Gráficos de Vendas e Pagamentos

| ID        | Requisito                                                                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------|
| RF-019.26 | O sistema deve exibir gráfico de rosca (donut) "Vendas por tipo de pagamento" mostrando: Crédito, Pix, Débito |
| RF-019.27 | O gráfico deve exibir percentuais e valores para cada tipo de pagamento                                       |

Gráficos de Origem e Localização

| ID        | Requisito                                                                                                               |
|-----------|-------------------------------------------------------------------------------------------------------------------------|
| RF-019.28 | O sistema deve exibir gráfico de barras horizontais "Acessos por fontes" mostrando origem dos acessos                   |
| RF-019.29 | O sistema deve exibir gráfico de rosca (donut) "Acessos por dispositivo" mostrando distribuição por tipo de dispositivo |
| RF-019.30 | O sistema deve exibir gráfico de barras horizontais "Estados com maior acesso" mostrando os estados com mais acessos    |
| RF-019.31 | O sistema deve exibir gráfico de barras horizontais "Cidades com mais acesso" mostrando as cidades com mais acessos     |

Interatividade dos Gráficos

| ID        | Requisito                                                                                    |
|-----------|----------------------------------------------------------------------------------------------|
| RF-019.32 | Os gráficos devem ser interativos: ao passar o mouse (hover), exibir valores exatos          |
| RF-019.33 | Os gráficos devem permitir clicar em elementos (barras, fatias) para ver detalhes ou filtrar |
| RF-019.34 | O sistema deve exibir tooltips informativos ao interagir com os gráficos                     |

Integração Google Analytics

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-019.35 | Todos os dados devem ser obtidos exclusivamente do Google Analytics                                      |
| RF-019.36 | O sistema deve filtrar os dados do Google Analytics pelo ID da atração selecionada                       |
| RF-019.37 | Os dados devem ser atualizados com intervalo definido pela equipe de desenvolvimento (não em tempo real) |
| RF-019.38 | O intervalo de atualização não deve prejudicar o desempenho do sistema                                   |

Mensagem de Integração Necessária

| ID        | Requisito                                                                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-019.39 | Se o Parceiro Comercial acessar este menu e não tiver conectado uma conta do Google Analytics, o sistema deve exibir mensagem solicitando a integração |
| RF-019.40 | A mensagem deve incluir instruções de como fazer a integração (link para RF-005 - Perfil)                                                              |
| RF-019.41 | Nenhum gráfico deve ser exibido enquanto não houver integração do Google Analytics                                                                     |

Regras de Negócio

| ID        | Regra                                                                                                    |
|-----------|----------------------------------------------------------------------------------------------------------|
| RN-019.01 | A integração com Google Analytics é obrigatória para visualizar os gráficos                              |
| RN-019.02 | Apenas o Parceiro Comercial dono da atração pode visualizar os dados da sua atração                      |
| RN-019.03 | O Administrador pode visualizar dados de todas as atrações                                               |
| RN-019.04 | Todos os dados são obtidos exclusivamente do Google Analytics (não do banco de dados do sistema)         |
| RN-019.05 | O filtro de período funciona da mesma forma que na tela "Totais da Atração" (RF-004)                     |
| RN-019.06 | A variação percentual compara o período selecionado com o período anterior equivalente                   |
| RN-019.07 | O "Tempo médio" é calculado como tempo médio de permanência na página da atração                         |
| RN-019.08 | A "Conversão" é calculada como: (Ingressos Vendidos / Acessos) × 100                                     |
| RN-019.09 | Os gráficos "Total de visitas" e "Total de ingressos" mostram dados por horário de acesso (não de venda) |
| RN-019.10 | Os dados demográficos (idade, gênero) vêm do Google Analytics                                            |
| RN-019.11 | Os dados de localização (estados, cidades) vêm do Google Analytics                                       |
| RN-019.12 | Os dados de dispositivo e fontes vêm do Google Analytics                                                 |
| RN-019.13 | Os dados de vendas por tipo de pagamento vêm do Google Analytics                                         |
| RN-019.14 | O sistema não oferece opção de exportar os gráficos/dados (PDF, Excel, CSV)                              |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                           |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-019.01 | Dado que o usuário acessa Detalhes da Atração > Gráficos Analytics, quando o Parceiro Comercial tem Google Analytics integrado, então deve visualizar todos os gráficos e métricas |
| CA-019.02 | Dado que o Parceiro Comercial acessa Gráficos Analytics sem ter Google Analytics integrado, então o sistema deve exibir mensagem solicitando a integração                          |
| CA-019.03 | Dado que o usuário altera o filtro de período para "7 Dias", então todos os gráficos e KPIs devem atualizar com dados dos últimos 7 dias                                           |
| CA-019.04 | Dado que o usuário passa o mouse sobre uma barra do gráfico, então deve exibir tooltip com valor exato                                                                             |
| CA-019.05 | Dado que o usuário clica em uma fatia do gráfico "Vendas por tipo de pagamento", então deve exibir detalhes ou filtrar os dados                                                    |
| CA-019.06 | Dado que o período selecionado é "30 Dias", quando os KPIs são calculados, então a variação percentual deve comparar com os 30 dias anteriores                                     |
| CA-019.07 | Dado que o Parceiro Comercial visualiza os gráficos, então deve ver apenas dados da atração selecionada                                                                            |
| CA-019.08 | Dado que o Administrador visualiza os gráficos, então deve ver dados de qualquer atração selecionada                                                                               |
| CA-019.09 | Dado que os dados são atualizados do Google Analytics, então o intervalo de atualização não deve causar lentidão no sistema                                                        |

Protótipo/Wireframe

Figura  - WF-025 - Detalhes da Atração/Gráficos Analytics

### 3.20 Detalhes da Atrações/Editar da Atração - Administrador
