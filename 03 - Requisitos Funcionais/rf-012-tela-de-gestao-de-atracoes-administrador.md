### 3.12 Tela de Gestão de Atrações - Administrador

**ID:** RF-012

Módulo: Gestão de Atrações

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador visualize, gerencie e acompanhe as atrações cadastradas no sistema. A tela apresenta uma lista de atrações com opções de busca, filtro e ações em massa (editar, excluir, inativar, ativar).

**Requisitos Detalhados**

**Estrutura da Tela**

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-012.01 | O sistema deve exibir o título "Gestão de Atrações" com subtítulo "Gerencie as atrações do sistema" |
| RF-012.02 | O sistema deve exibir campo de pesquisa por texto (busca por ID, nome ou parceiro comercial)        |
| RF-012.03 | O sistema deve exibir botão "Filtro" ao lado do campo de busca                                      |
| RF-012.04 | O sistema deve exibir botão "Adicionar Atração" que abre o modal de cadastro (RF-013)               |

**Sistema de Abas**

| ID        | Requisito                                                                       |
|-----------|---------------------------------------------------------------------------------|
| RF-012.05 | O sistema deve exibir abas para filtrar atrações: "Ativos", "Inativos", "Todos" |
| RF-012.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela                |
| RF-012.07 | A aba "Ativos" exibe atrações com status: Ativo, Pendente de Contrato, Rascunho |
| RF-012.08 | A aba "Inativos" exibe atrações com status: Inativo, Expirado                   |
| RF-012.09 | A aba "Todos" exibe todas as atrações independente do status                    |

**Tabela de Atrações**

| ID        | Requisito                                                                                                                                  |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| RF-012.10 | O sistema deve exibir tabela com as colunas: Checkbox, ID da Atração, Nome (com foto), Parceiro Comercial (badge), Status, Data de criação |
| RF-012.11 | A coluna Nome deve exibir a foto de capa da atração (thumbnail) + nome da atração                                                          |
| RF-012.12 | A coluna Parceiro Comercial deve exibir o nome do parceiro em formato badge                                                                |
| RF-012.13 | A coluna Status deve exibir badge colorido conforme o status da atração                                                                    |
| RF-012.14 | Cada coluna deve possuir ícone de ordenação (ASC/DESC)                                                                                     |
| RF-012.15 | A ordenação padrão deve ser por ID da Atração DESC (mais recentes primeiro)                                                                |

**Status das Atrações**

| Status               | Cor do Badge   | Descrição                                           |
|----------------------|----------------|-----------------------------------------------------|
| Rascunho             | 🔘 Cinza        | Atração em preenchimento, não finalizada            |
| Pendente de Contrato | 🟡 Amarelo      | Atração cadastrada aguardando contrato ser assinado |
| Ativo                | 🟢 Verde        | Atração publicada e visível no portal               |
| Inativo              | 🔴 Vermelho     | Atração desativada manualmente                      |
| Expirado             | 🟠 Laranja      | Contrato da atração expirou                         |

**Busca e Filtros**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-012.16 | O campo de busca deve pesquisar por: ID, Nome da atração, Nome do Parceiro Comercial |
| RF-012.17 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa            |
| RF-012.18 | O botão "Filtro" deve abrir painel com os filtros disponíveis                        |

**Filtros Disponíveis:**

| Filtro             | Tipo             | Descrição                                  |
|--------------------|------------------|--------------------------------------------|
| Parceiro Comercial | Select com busca | Filtrar por parceiro específico            |
| Status             | Multi-select     | Filtrar por um ou mais status              |
| Data de criação    | Range de datas   | Filtrar por período de criação             |
| Com contrato ativo | Checkbox         | Filtrar apenas atrações com contrato ativo |

**Seleção e Ações em Massa**

| ID        | Requisito                                                                                                               |
|-----------|-------------------------------------------------------------------------------------------------------------------------|
| RF-012.19 | O sistema deve permitir seleção múltipla via checkbox na primeira coluna                                                |
| RF-012.20 | Ao selecionar uma ou mais atrações, o sistema deve exibir barra de ações com: contador "Selecionados X", botões de ação |
| RF-012.21 | O checkbox do cabeçalho seleciona/deseleciona todas as atrações da página atual                                         |

**Ações Disponíveis:**

| Ação                  | Quando Aparece                  | Comportamento                                        |
|-----------------------|---------------------------------|------------------------------------------------------|
| Editar                | Apenas 1 selecionado            | Abre modal de edição (RF-013) com campos preenchidos |
| Excluir               | 1 ou mais selecionados          | Exibe confirmação e executa soft delete              |
| Inativar selecionados | Aba "Ativos", 1+ selecionados   | Muda status para "Inativo"                           |
| Ativar selecionados   | Aba "Inativos", 1+ selecionados | Muda status para "Ativo" (se tiver contrato ativo)   |

**Ação de Clique na Linha**

| ID        | Requisito                                                                                                                           |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| RF-012.22 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir o modal de edição da atração (RF-013) em modo visualização |
| RF-012.23 | No modal de visualização, todos os campos devem estar desabilitados para edição                                                     |
| RF-012.24 | O modal de visualização deve exibir botão "Habilitar Edição" para permitir alterações                                               |

**Paginação**

| ID        | Requisito                                                                                                  |
|-----------|------------------------------------------------------------------------------------------------------------|
| RF-012.25 | O sistema deve exibir por padrão 10 registros por página                                                   |
| RF-012.26 | O sistema deve permitir alterar para: 10, 20, 50, 100 registros por página                                 |
| RF-012.27 | O sistema deve exibir navegação: Primeira página, Anterior, Indicador (X a Y de Z), Próxima, Última página |

**Regras de Negócio**

| #         | Regra                                                                                                                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-012.01 | Soft Delete: Ao excluir uma atração, o sistema deve marcar como "Excluído" no banco de dados (não remove fisicamente)                                                                                                                                   |
| RN-012.02 | Impacto no Contrato: Ao excluir ou inativar uma atração que possui contrato vinculado, o sistema deve exibir alerta: "Esta atração possui contrato vinculado. Ao excluir/inativar, o contrato será alterado para status 'Cancelado'. Deseja continuar?" |
| RN-012.03 | Recuperação: Atrações excluídas NÃO podem ser recuperadas pelo Administrador (apenas equipe de TI via banco de dados)                                                                                                                                   |
| RN-012.04 | Reativação: Atrações inativadas podem ser reativadas pela aba "Inativos", desde que possuam contrato ativo                                                                                                                                              |
| RN-012.05 | Reativação sem contrato: Ao tentar ativar uma atração sem contrato ativo, exibir mensagem: "Esta atração não possui contrato ativo. Crie um contrato antes de ativá-la."                                                                                |
| RN-012.06 | Visibilidade no Portal: Apenas atrações com status "Ativo" são visíveis para turistas no portal público                                                                                                                                                 |

Critérios de Aceitação

| #         | Critério                                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-012.01 | Dado que o Administrador acessa a tela de Gestão de Atrações, quando a página carrega, então deve exibir a lista de atrações ativas ordenadas por ID DESC       |
| CA-012.02 | Dado que o Administrador seleciona uma atração e clica em "Editar", quando o modal abre, então deve exibir todos os dados da atração nos campos correspondentes |
| CA-012.03 | Dado que o Administrador exclui uma atração com contrato vinculado, quando confirma a exclusão, então o contrato deve ter seu status alterado para "Cancelado"  |
| CA-012.04 | Dado que o Administrador clica em uma linha da tabela, quando o modal abre, então os campos devem estar desabilitados (modo visualização)                       |
| CA-012.05 | Dado que o Administrador pesquisa por "Ópera", quando a busca é executada, então deve retornar todas as atrações que contenham "Ópera" no nome                  |

**Protótipo/Wireframe**

Figura  - WF-012 - Gestão de Atrações

### 3.13 Tela de Gestão de Atrações/Adicionar Atração - Administrador
