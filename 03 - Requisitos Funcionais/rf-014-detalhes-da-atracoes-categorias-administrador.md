### 3.14 Detalhes da Atrações/Categorias – Administrador

**ID:** RF-014

**Módulo:** Detalhes da Atração &gt; Categorias

**Perfis com Acesso:** Administrador, Parceiro Comercial, Editor

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve permitir a gestão centralizada das categorias de ingresso (tipos de público) vinculadas a uma atração específica. Categorias definem os tipos de ingresso disponíveis (Ex: Estudante, Adulto, Idoso, Doador de Sangue, Morador de Curitiba), enquanto valores e quantidades são configurados separadamente na Gestão de Ingressos/Lotes.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-014.01 | O sistema deve exibir título "Categorias" com subtítulo "Gerencie as categorias da atração" |
| RF-014.02 | O sistema deve exibir campo de pesquisa para buscar por ID ou Nome da categoria             |
| RF-014.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                 |
| RF-014.04 | O sistema deve exibir botão "Adicionar Categoria" que abre o modal de criação               |

Sistema de Abas

| ID        | Requisito                                                                                    |
|-----------|----------------------------------------------------------------------------------------------|
| RF-014.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos"                      |
| RF-014.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela                             |
| RF-014.07 | Ao alternar entre abas, a tabela deve atualizar exibindo apenas os registros correspondentes |

Tabela de Categorias

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-014.08 | O sistema deve exibir tabela com colunas: Checkbox (seleção), ID, Categoria (nome), Status |
| RF-014.09 | A coluna Status deve exibir badges: "Ativo" (verde) ou "Inativo" (cinza)                   |
| RF-014.10 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                        |
| RF-014.11 | A tabela deve ser ordenada por ID DESC por padrão                                          |

Busca e Filtros

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-014.12 | O campo de pesquisa deve buscar por ID ou Nome da categoria                                     |
| RF-014.13 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                       |
| RF-014.14 | O botão Filtro deve abrir painel com filtros: Status (Ativo/Inativo), Data de Criação (período) |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-014.15 | O sistema deve permitir seleção múltipla via checkbox                                                       |
| RF-014.16 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Editar, Excluir, Inativar (toggle) |
| RF-014.17 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                            |

Ações Disponíveis

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-014.18 | **Editar**  : Disponível apenas quando 1 item selecionado. Abre modal de edição                             |
| RF-014.19 | **Excluir**  : Exibe confirmação "Deseja excluir X categoria(s) selecionada(s)?". Permite exclusão em massa |
| RF-014.20 | **Inativar**  : Altera status para "Inativo". Permite inativação em massa                                   |
| RF-014.21 | **Ativar**  (aba Inativos): Altera status para "Ativo". Permite ativação em massa                           |
| RF-014.22 | O toggle Inativar/Ativar na barra de ações deve alternar conforme a aba ativa                               |

Ação de Clique na Linha

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-014.23 | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-014.24 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-014.25 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-014.26 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Categoria

| ID        | Requisito                                                                                                                                  |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| RF-014.27 | O modal deve exibir título dinâmico: "Adicionar Categoria" (novo), "Editar Categoria" (edição) ou "Visualizar Categoria" (somente leitura) |
| RF-014.28 | Campos do modal: ID (somente leitura, gerado automaticamente), Nome da Categoria (obrigatório, máx 100 caracteres), Status (Ativo/Inativo) |
| RF-014.29 | No modo Adicionar: campo ID não aparece, Status padrão "Ativo"                                                                             |
| RF-014.30 | No modo Editar: todos os campos editáveis exceto ID                                                                                        |
| RF-014.31 | No modo Visualizar: todos os campos somente leitura                                                                                        |
| RF-014.32 | O modal deve exibir campos de auditoria (somente leitura): Data de Criação, Última Atualização                                             |
| RF-014.33 | Botões: Salvar e Cancelar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                                                      |
| RF-014.34 | Ao salvar nova categoria, o sistema deve gerar ID único automaticamente e vincular à atração atual                                         |
| RF-014.35 | Ao salvar, o modal deve fechar e a tabela deve ser atualizada                                                                              |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                     |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-014.01 | Categorias são sempre vinculadas a uma atração específica (não são globais)                                                                                                               |
| RN-014.02 | O sistema deve impedir a exclusão de categorias que já foram utilizadas em ingressos vendidos. Mensagem: "Esta categoria não pode ser excluída pois possui ingressos vendidos vinculados" |
| RN-014.03 | O sistema deve impedir a inativação de categorias com ingressos com status "Vendido" ou "Validado" pendentes                                                                              |
| RN-014.04 | O nome da categoria deve ser único dentro da mesma atração. Mensagem de erro: "Já existe uma categoria com este nome nesta atração"                                                       |
| RN-014.05 | Categorias criadas aqui ficam disponíveis para seleção na Gestão de Ingressos/Lotes                                                                                                       |
| RN-014.06 | Categorias inativas não aparecem como opção na criação de novos ingressos/lotes                                                                                                           |
| RN-014.07 | O ID da categoria é gerado automaticamente pelo sistema de forma incremental                                                                                                              |
| RN-014.08 | Exclusão é soft delete (marcação no banco de dados). Categorias excluídas não aparecem em nenhuma aba                                                                                     |
| RN-014.09 | Categorias excluídas só podem ser recuperadas pela equipe de TI via banco de dados                                                                                                        |
| RN-014.10 | Esta funcionalidade é a mesma acessada pelo botão "Adicionar categoria" no cadastro de atrações (RF-013)                                                                                  |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                           |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-014.01 | Dado que o usuário acessa Detalhes da Atração > Categorias, então deve visualizar a lista de categorias da atração selecionada na aba "Ativos"                     |
| CA-014.02 | Dado que o usuário clica em "Adicionar Categoria", quando preenche o nome e salva, então a categoria deve aparecer na lista com status "Ativo"                     |
| CA-014.03 | Dado que existe uma categoria vinculada a ingressos vendidos, quando o usuário tenta excluí-la, então o sistema deve exibir mensagem de erro e impedir a exclusão  |
| CA-014.04 | Dado que o usuário seleciona múltiplas categorias, quando clica em "Inativar", então todas devem ter seu status alterado para "Inativo"                            |
| CA-014.05 | Dado que o usuário está na aba "Inativos", quando seleciona categorias e clica em "Ativar", então elas devem voltar para status "Ativo" e aparecer na aba "Ativos" |
| CA-014.06 | Dado que o usuário clica em uma linha da tabela (fora do checkbox), então deve abrir o modal de visualização com campos somente leitura                            |
| CA-014.07 | Dado que o usuário tenta criar categoria com nome já existente na atração, então o sistema deve exibir erro de duplicidade                                         |
| CA-014.08 | Dado que o usuário altera a paginação para 50 itens, então a tabela deve exibir até 50 registros por página                                                        |

**Protótipo/Wireframe**

Figura  - WF-016 - Detalhes da Atração/Categorias.png

### 3.15 Detalhes da Atrações/Pesquisar Ingresso – Administrador
