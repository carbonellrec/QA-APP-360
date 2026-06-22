### 3.6 Gestão de Usuários - Administrador

**ID:** RF-006

Módulo: Gestão de Usuários

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador gerencie os usuários do sistema, incluindo listagem, busca, filtros, visualização, cadastro, edição, inativação, ativação e exclusão de usuários, definindo seus perfis de acesso e dados de contato.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-006.01 | O sistema deve exibir o título "Gestão de Usuários" com subtítulo "Gerencie os usuários do sistema" |
| RF-006.02 | O sistema deve exibir campo de pesquisa por texto (busca por ID, nome ou e-mail)                    |
| RF-006.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                         |
| RF-006.04 | O sistema deve exibir botão "Adicionar usuário" para cadastrar novo usuário                         |
| RF-006.05 | O sistema deve exibir abas para filtrar por status: "Ativos", "Inativos", "Todos"                   |
| RF-006.06 | O sistema deve exibir a aba "Ativos" selecionada por padrão                                         |

Tabela de Usuários

| ID        | Requisito                                                                                                           |
|-----------|---------------------------------------------------------------------------------------------------------------------|
| RF-006.07 | O sistema deve exibir tabela com os usuários cadastrados conforme a aba selecionada                                 |
| RF-006.08 | A tabela deve exibir as colunas: Checkbox, User ID, Nome (com foto e e-mail), Perfil, Data de criação, Último login |
| RF-006.09 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                               |
| RF-006.10 | A ordenação padrão deve ser por User ID decrescente (mais recente primeiro)                                         |
| RF-006.11 | A coluna Nome deve exibir: foto do usuário (ou avatar padrão), nome completo e e-mail                               |
| RF-006.12 | A coluna Perfil deve exibir badge visual com o nome do perfil                                                       |
| RF-006.13 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização                      |

Seleção e Ações em Massa

| ID        | Requisito                                                                                             |
|-----------|-------------------------------------------------------------------------------------------------------|
| RF-006.14 | O sistema deve exibir checkbox na primeira coluna para seleção de usuários                            |
| RF-006.15 | O sistema deve permitir selecionar múltiplos usuários via checkbox                                    |
| RF-006.16 | Ao selecionar um ou mais usuários, o sistema deve exibir barra de ações com contador "Selecionados X" |
| RF-006.17 | Na aba "Ativos", a barra de ações deve exibir: "Editar", "Excluir", "Inativar selecionados"           |
| RF-006.18 | Na aba "Inativos", a barra de ações deve exibir: "Editar", "Excluir", "Ativar selecionados"           |
| RF-006.19 | O botão "Editar" deve estar habilitado apenas quando  **1 usuário**  estiver selecionado              |
| RF-006.20 | Os botões "Excluir", "Inativar" e "Ativar" devem funcionar para múltiplos usuários selecionados       |

Paginação

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-006.21 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100   |
| RF-006.22 | O sistema deve exibir indicador de registros: "X a Y de Z"                                       |
| RF-006.23 | O sistema deve exibir navegação: primeira página, anterior, página atual, próxima, última página |

Colunas da Tabela

| Coluna          | Conteúdo                 | Ordenável   | Observação                              |
|-----------------|--------------------------|-------------|-----------------------------------------|
| Checkbox        | ☐                        | ❌           | Seleção múltipla                        |
| User ID         | ID numérico              | ✅           | Ordenação padrão DESC                   |
| Nome            | Foto + Nome + E-mail     | ✅           | Ordena por nome                         |
| Perfil          | Badge com nome do perfil | ✅           | Administrador, Parceiro Comercial, etc. |
| Data de criação | DD/MM/AAAA HH:MM:SS      | ✅           | Data de cadastro                        |
| Último login    | DD/MM/AAAA HH:MM:SS      | ✅           | Última autenticação                     |

Abas de Status

| Aba      | Descrição                            | Ações Disponíveis                |
|----------|--------------------------------------|----------------------------------|
| Ativos   | Usuários com status ativo            | Editar, Excluir, Inativar        |
| Inativos | Usuários com status inativo          | Editar, Excluir, Ativar          |
| Todos    | Todos os usuários (exceto excluídos) | Editar, Excluir, Inativar/Ativar |

Filtros Avançados (Botão Filtro)

| Filtro          | Tipo               | Opções                                                             |
|-----------------|--------------------|--------------------------------------------------------------------|
| Perfil          | Multi-select       | Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente |
| Data de criação | Intervalo de datas | Data inicial - Data final                                          |
| Último login    | Intervalo de datas | Data inicial - Data final                                          |
| Nunca logou     | Checkbox           | Usuários que nunca fizeram login                                   |

Ações Detalhadas

Visualizar (Clicar na linha)

| ID        | Requisito                                                                        |
|-----------|----------------------------------------------------------------------------------|
| RF-006.24 | Ao clicar em uma linha da tabela, o sistema deve abrir modal de visualização     |
| RF-006.25 | O modal de visualização deve exibir todos os campos do usuário (conforme RF-007) |
| RF-006.26 | Todos os campos devem estar  **desabilitados para edição**  (somente leitura)    |
| RF-006.27 | O modal deve exibir botão "Fechar" para retornar à listagem                      |

Editar (Via seleção)

| ID        | Requisito                                                                     |
|-----------|-------------------------------------------------------------------------------|
| RF-006.28 | O botão "Editar" deve estar habilitado apenas com  **1 usuário selecionado**  |
| RF-006.29 | Ao clicar em "Editar", o sistema deve abrir modal de edição (conforme RF-007) |
| RF-006.30 | O modal de edição deve permitir alteração dos campos editáveis                |

Excluir

| ID        | Requisito                                                                               |
|-----------|-----------------------------------------------------------------------------------------|
| RF-006.31 | Ao clicar em "Excluir", o sistema deve exibir modal de confirmação                      |
| RF-006.32 | O modal deve informar a quantidade de usuários que serão excluídos                      |
| RF-006.33 | Ao confirmar, o sistema deve realizar  **soft delete**  (marcar como excluído no banco) |
| RF-006.34 | Usuários excluídos  **não devem**  aparecer em nenhuma aba da listagem                  |
| RF-006.35 | O sistema deve exibir mensagem de sucesso após exclusão                                 |

Inativar

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-006.36 | Ao clicar em "Inativar selecionados", o sistema deve exibir modal de confirmação       |
| RF-006.37 | Ao confirmar, o sistema deve alterar o status dos usuários para "Inativo"              |
| RF-006.38 | Usuários inativados devem aparecer na aba "Inativos"                                   |
| RF-006.39 | O sistema deve exibir mensagem de sucesso informando quantos usuários foram inativados |

Ativar (Aba Inativos)

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-006.40 | Na aba "Inativos", ao selecionar usuários, exibir botão "Ativar selecionados"        |
| RF-006.41 | Ao clicar em "Ativar selecionados", o sistema deve exibir modal de confirmação       |
| RF-006.42 | Ao confirmar, o sistema deve alterar o status dos usuários para "Ativo"              |
| RF-006.43 | Usuários ativados devem aparecer na aba "Ativos"                                     |
| RF-006.44 | O sistema deve exibir mensagem de sucesso informando quantos usuários foram ativados |

Regras de Negócio

| ID        | Regra                                                                                                 |
|-----------|-------------------------------------------------------------------------------------------------------|
| RN-006.01 | Apenas o perfil  **Administrador**  tem acesso a este módulo                                          |
| RN-006.02 | O Administrador  **não pode**  inativar ou excluir a si mesmo                                         |
| RN-006.03 | Ao inativar um usuário, sua sessão ativa deve ser encerrada imediatamente                             |
| RN-006.04 | Usuários inativos  **não podem**  fazer login nem ser utilizados em outras rotinas do sistema         |
| RN-006.05 | Usuários inativos  **podem**  ser reativados pelo Administrador via aba "Inativos"                    |
| RN-006.06 | A exclusão é um  **soft delete**  - o registro é marcado como excluído no banco de dados              |
| RN-006.07 | Usuários excluídos  **não podem**  ser recuperados pelo Administrador (apenas equipe de TI via banco) |
| RN-006.08 | Usuários excluídos  **não aparecem**  em nenhuma listagem do sistema                                  |
| RN-006.09 | O botão "Editar" só é habilitado quando  **exatamente 1 usuário**  está selecionado                   |
| RN-006.10 | A pesquisa deve buscar em: User ID, Nome e E-mail (case insensitive)                                  |
| RN-006.11 | A ordenação padrão é por  **User ID decrescente**  (mais recente primeiro)                            |
| RN-006.12 | A paginação padrão exibe  **10 registros**  por página                                                |
| RN-006.13 | Usuários que nunca logaram devem exibir "-" ou "Nunca" na coluna "Último login"                       |
| RN-006.14 | A senha do usuário  **não deve**  ser exibida em nenhuma tela (segurança)                             |

Barra de Ações por Aba

| Aba      | Ações                                                               |
|----------|---------------------------------------------------------------------|
| Ativos   | [Selecionados X] [Editar] [Excluir] [Inativar selecionados]         |
| Inativos | [Selecionados X] [Editar] [Excluir] [Ativar selecionados]           |
| Todos    | [Selecionados X] [Editar] [Excluir] [Inativar/Ativar selecionados]* |

O botão muda conforme o status dos usuários selecionados

Critérios de Aceitação

| ID        | Critério                                         | Resultado Esperado                                                     |
|-----------|--------------------------------------------------|------------------------------------------------------------------------|
| CA-006.01 | Acessar Gestão de Usuários como Administrador    | Tela exibida com aba "Ativos" selecionada                              |
| CA-006.02 | Visualizar lista de usuários                     | Tabela exibe usuários ativos com todas as colunas                      |
| CA-006.03 | Pesquisar por nome "João"                        | Lista filtrada exibindo usuários com "João" no nome                    |
| CA-006.04 | Pesquisar por e-mail "@gmail"                    | Lista filtrada exibindo usuários com "@gmail" no e-mail                |
| CA-006.05 | Clicar em "Filtro"                               | Modal/dropdown de filtros avançados é exibido                          |
| CA-006.06 | Filtrar por perfil "Editor"                      | Lista exibe apenas usuários com perfil Editor                          |
| CA-006.07 | Clicar na aba "Inativos"                         | Lista atualiza exibindo apenas usuários inativos                       |
| CA-006.08 | Clicar na aba "Todos"                            | Lista atualiza exibindo usuários ativos e inativos                     |
| CA-006.09 | Clicar em uma linha da tabela                    | Modal de visualização abre com campos desabilitados                    |
| CA-006.10 | Selecionar 1 usuário via checkbox                | Barra de ações exibe: "Selecionados 1", Editar, Excluir, Inativar      |
| CA-006.11 | Selecionar 3 usuários via checkbox               | Barra de ações exibe: "Selecionados 3", botão Editar  **desabilitado** |
| CA-006.12 | Clicar em "Editar" com 1 usuário selecionado     | Modal de edição abre com campos habilitados                            |
| CA-006.13 | Clicar em "Excluir" com usuários selecionados    | Modal de confirmação exibe quantidade a ser excluída                   |
| CA-006.14 | Confirmar exclusão                               | Usuários removidos da lista + mensagem de sucesso                      |
| CA-006.15 | Verificar usuário excluído                       | Usuário não aparece em nenhuma aba (Ativos, Inativos, Todos)           |
| CA-006.16 | Clicar em "Inativar selecionados"                | Modal de confirmação é exibido                                         |
| CA-006.17 | Confirmar inativação                             | Usuários movidos para aba "Inativos" + mensagem de sucesso             |
| CA-006.18 | Na aba Inativos, clicar em "Ativar selecionados" | Modal de confirmação é exibido                                         |
| CA-006.19 | Confirmar ativação                               | Usuários movidos para aba "Ativos" + mensagem de sucesso               |
| CA-006.20 | Tentar inativar a si mesmo                       | Mensagem "Não é possível inativar seu próprio usuário"                 |
| CA-006.21 | Tentar excluir a si mesmo                        | Mensagem "Não é possível excluir seu próprio usuário"                  |
| CA-006.22 | Ordenar por "Nome" ascendente                    | Lista reordenada de A-Z                                                |
| CA-006.23 | Alterar paginação para 50                        | Lista exibe até 50 registros por página                                |
| CA-006.24 | Navegar para próxima página                      | Lista exibe próximos registros                                         |
| CA-006.25 | Clicar em "Adicionar usuário"                    | Modal de cadastro é aberto (RF-007)                                    |

Protótipo/Wireframe

Figura  - WF-005 - Gestão de Usuários.png

### 3.7 Cadastro de Usuários - Administrador
