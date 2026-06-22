### 3.15 Detalhes da Atrações/Pesquisar Ingresso – Administrador

**ID:** RF-015

**Módulo:** Detalhes da Atração &gt; Pesquisar Ingresso

**Perfis:** Administrador, Parceiro Comercial, Editor, Leitor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a pesquisa, visualização e gestão dos ingressos emitidos para uma atração específica. A tela apresenta uma lista de ingressos com opções de busca, filtro e ações em massa (validar, reenviar, visualizar QR Code, cancelar, inativar). Esta funcionalidade serve como alternativa para validação manual de ingressos quando houver problemas com o leitor de QR Code.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-015.01 | O sistema deve exibir título "Pesquisar Ingresso" com subtítulo "Gerencie os ingressos emitidos" |
| RF-015.02 | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                 |
| RF-015.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                      |
| RF-015.04 | A tela NÃO possui botão de adicionar (ingressos são criados apenas via compra)                   |

Sistema de Abas

| ID        | Requisito                                                               |
|-----------|-------------------------------------------------------------------------|
| RF-015.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
| RF-015.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
| RF-015.07 | A aba "Ativos" deve exibir ingressos com status: Vendido, Validado      |
| RF-015.08 | A aba "Inativos" deve exibir ingressos com status: Cancelado, Inativado |
| RF-015.09 | A aba "Todos" deve exibir todos os ingressos independente do status     |

Tabela de Ingressos

| ID        | Requisito                                                                                                                 |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RF-015.10 | O sistema deve exibir tabela com colunas: Checkbox, ID, Código, Status, Atração, Categoria, Localização, Data Hora Pedido |
| RF-015.11 | A coluna "Status" deve exibir badges coloridos conforme o status do ingresso                                              |
| RF-015.12 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                                                       |
| RF-015.13 | A tabela deve ser ordenada por Data Hora Pedido DESC por padrão                                                           |

Status dos Ingressos

| ID        | Requisito                                                                          |
|-----------|------------------------------------------------------------------------------------|
| RF-015.14 | Vendido (badge verde): Ingresso emitido, pagamento confirmado, ainda não utilizado |
| RF-015.15 | Validado (badge azul): Ingresso já utilizado para entrada na atração               |
| RF-015.16 | Cancelado (badge cinza): Ingresso estornado e cancelado                            |
| RF-015.17 | Inativado (badge vermelho): Ingresso bloqueado manualmente pelo administrador      |

Busca e Filtros

| ID        | Requisito                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------|
| RF-015.18 | O campo de pesquisa deve buscar por: ID, Código, Atração, Categoria, Localização                       |
| RF-015.19 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                              |
| RF-015.20 | O botão Filtro deve abrir painel com filtros: Status, Categoria, Data do Pedido (período), Localização |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                                                                         |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-015.21 | O sistema deve permitir seleção múltipla via checkbox                                                                                                             |
| RF-015.22 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Validar ingresso, Reenviar ingresso, Visualizar QR Code, Cancelar, Inativar selecionados |
| RF-015.23 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                                                                                  |

Ações Disponíveis

| ID        | Requisito                                                                                                                                |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------|
| RF-015.24 | Validar ingresso: Altera status de "Vendido" para "Validado". Permite validação em massa. Funciona sem necessidade de escanear QR Code   |
| RF-015.25 | Reenviar ingresso: Reenvia o ingresso por e-mail E SMS para o cliente. Permite reenvio em massa                                          |
| RF-015.26 | Visualizar QR Code: Abre modal exibindo a imagem do QR Code. Permite download e impressão. Disponível apenas para 1 ingresso selecionado |
| RF-015.27 | Cancelar: Comportamento varia conforme status atual do ingresso (ver Regras de Negócio)                                                  |
| RF-015.28 | Inativar selecionados: Altera status para "Inativado". Permite inativação em massa. Bloqueia o ingresso na entrada da atração            |

Ação de Clique na Linha

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-015.29 | Ao clicar em uma linha (fora do checkbox), abrir modal "Detalhes do Ingresso" (RF-016) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-015.30 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-015.31 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-015.32 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Regras de Negócio

| ID        | Regra                                                                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RN-015.01 | Ingressos são criados automaticamente quando o pagamento do pedido é confirmado                                                      |
| RN-015.02 | Um pedido pode gerar múltiplos ingressos (ex: cliente compra 3 ingressos no mesmo pedido)                                            |
| RN-015.03 | Cancelar ingresso "Validado": Sistema pede confirmação. Se confirmado, status volta para "Vendido" (permite nova entrada)            |
| RN-015.04 | Cancelar ingresso "Vendido": Sistema exibe mensagem de confirmação com aviso de estorno. Se confirmado, status muda para "Cancelado" |
| RN-015.05 | Ingressos com status "Inativado" são bloqueados ao serem escaneados na entrada. Sistema exibe notificação ao validador               |
| RN-015.06 | A ação "Validar ingresso" só está disponível para ingressos com status "Vendido"                                                     |
| RN-015.07 | A ação "Cancelar" só está disponível para ingressos com status "Vendido" ou "Validado"                                               |
| RN-015.08 | A ação "Inativar" só está disponível para ingressos com status "Vendido"                                                             |
| RN-015.09 | Ingressos com status "Cancelado" ou "Inativado" não podem ter ações executadas (apenas visualização)                                 |
| RN-015.10 | O perfil Leitor tem acesso limitado: pode apenas pesquisar e visualizar, não pode executar ações                                     |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                          |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-015.01 | Dado que o usuário acessa Detalhes da Atração > Pesquisar Ingresso, então deve visualizar a lista de ingressos na aba "Ativos"                                                    |
| CA-015.02 | Dado que o usuário seleciona um ingresso com status "Vendido" e clica em "Validar", então o status deve mudar para "Validado"                                                     |
| CA-015.03 | Dado que o usuário seleciona um ingresso com status "Validado" e clica em "Cancelar", quando confirma, então o status deve voltar para "Vendido"                                  |
| CA-015.04 | Dado que o usuário seleciona um ingresso com status "Vendido" e clica em "Cancelar", quando confirma, então o status deve mudar para "Cancelado" e o pagamento deve ser estornado |
| CA-015.05 | Dado que o usuário clica em "Reenviar ingresso", então o ingresso deve ser enviado por e-mail E SMS ao cliente                                                                    |
| CA-015.06 | Dado que um ingresso está com status "Inativado" e é escaneado na entrada, então o sistema deve bloquear e exibir notificação ao validador                                        |
| CA-015.07 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de detalhes do ingresso                                                                                 |

**Protótipo/Wireframe**

Figura  - Detalhes da Atrações/Pesquisar Ingresso – Administrador

### 3.16 Detalhes da Atrações/Pesquisar Ingresso/Detalhes – Administrador
