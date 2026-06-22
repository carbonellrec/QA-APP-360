### 3.3 Dashboard – Administrador

**ID:** RF-003

**Módulo:** Dashboard

**Perfis com Acesso** : Administrador

**Prioridade:** Alta (Essencial)

Descrição: O sistema deve exibir um painel de controle (Dashboard) para o Administrador com indicadores consolidados de vendas, atrações e métricas gerais do sistema, permitindo uma visão geral do negócio.

Requisitos Detalhados

| ID        | Requisito                                                                          |
|-----------|------------------------------------------------------------------------------------|
| RF-003.01 | O sistema deve exibir as atrações em cards com indicadores resumidos (KPIs)        |
| RF-003.02 | O sistema deve exibir uma lista das atrações cadastradas com informações resumidas |
| RF-003.03 | O sistema deve permitir filtrar os dados por período (data inicial e data final)   |
| RF-003.04 | O sistema deve permitir clicar em uma atração para visualizar seus detalhes        |
| RF-003.05 | O sistema deve exibir gráficos de vendas e/ou indicadores visuais                  |
| RF-003.06 | O sistema deve permitir pesquisar atrações pelo nome, cidade, estado, data e id.   |
| RF-003.07 | O sistema deverá exibir botão para ordenação por nome ou data.                     |

Regras de Negócio

| ID        | Regra                                                                       |
|-----------|-----------------------------------------------------------------------------|
| RN-003.01 | O Dashboard é exclusivo para o perfil  **Administrador**  nesta versão      |
| RN-003.02 | Os dados exibidos devem ser atualizados em tempo real ou com refresh manual |
| RN-003.03 | O filtro de período padrão deve considerar os últimos 30 dias               |

Indicadores Sugeridos (Cards)

| Indicador          | Descrição                                    |
|--------------------|----------------------------------------------|
| Ingressos Vendidos | Quantidade de ingressos vendidos no período  |
| Cortesias          | Quantidade de ingressos cortesia emitidos    |
| Total de ingressos | Quantidade de total de ingressos emitidos    |
| Total de Vendas    | Valor total de vendas no período selecionado |

Critérios de Aceitação

| ID        | Critério                             | Resultado Esperado                                            |
|-----------|--------------------------------------|---------------------------------------------------------------|
| CA-003.01 | Acessar Dashboard como Administrador | Cards de KPIs exibidos com dados corretos                     |
| CA-003.02 | Aplicar filtro de período            | Dados atualizados conforme período selecionado                |
| CA-003.03 | Clicar em uma atração da lista       | Sistema redireciona para tela de Detalhes da Atração (RF-004) |
| CA-003.04 | Pesquisar atração por nome           | Lista filtrada exibindo apenas atrações correspondentes       |
| CA-003.05 | Acessar Dashboard com outro perfil   | Acesso negado ou menu não visível                             |

Protótipo/Wireframe

Figura  - WF-002 - Dashboard

### 3.4 Detalhes da Atração / Totais da Atração - Administrador
