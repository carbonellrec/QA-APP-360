### 3.21 Detalhes da Atrações/Usuários - Administrador

**ID:** RF-021

**Módulo** : Gestão de Atrações &gt; Detalhes da Atração &gt; Usuários

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador e Parceiro Comercial o cadastro e a gestão de usuários vinculados a uma atração específica. A tela é acessada pelo menu Detalhes da Atração &gt; Usuários e permite listar os usuários da atração, vincular usuários já cadastrados (perfis Editor, Leitor, Agência e Agente), criar novos usuários Editor ou Leitor no contexto da atração, visualizar, editar e desvincular usuários. Não é permitido vincular ou cadastrar usuários com perfil Parceiro Comercial nem Turista nesta tela.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-021.01 | O sistema deve exibir título e subtítulo da tela no contexto da atração (ex.: "Usuários - [Nome da Atração]").                                                                                                                                                                                                        |
| RF-021.02 | O sistema deve exibir campo de pesquisa por texto (busca por id, nome ou e-mail) para localizar usuários.                                                                                                                                                                                                             |
| RF-021.03 | O sistema deve exibir botão "Filtro" para filtros avançados (ativos, inativos, todos e demais critérios).                                                                                                                                                                                                             |
| RF-021.04 | O sistema deve exibir botão "Adicionar usuário" para vincular usuário existente ou criar novo no contexto da atração.                                                                                                                                                                                                 |
| RF-021.05 | O sistema deve exibir abas para filtrar por status: "Ativos", "Inativos", "Todos".                                                                                                                                                                                                                                    |
| RF-021.06 | O sistema deve exibir a aba "Ativos" selecionada por padrão.                                                                                                                                                                                                                                                          |
| RF-021.07 | O sistema deve exibir tabela com botões de ação (visualizar, editar, desvincular) e colunas: id, nome, e-mail, data de criação, último acesso, ativo.                                                                                                                                                                 |
| RF-021.08 | O sistema deve permitir ordenar as colunas da tabela (ASC/DESC).                                                                                                                                                                                                                                                      |
| RF-021.09 | O sistema deve apresentar filtros para ativos, inativos e todos conforme as abas e o botão Filtro.                                                                                                                                                                                                                    |
| RF-021.10 | Ao incluir novo usuário vinculado à atração, o sistema deve enviar senha provisória por e-mail para o primeiro acesso.                                                                                                                                                                                                |
| RF-021.11 | O sistema deve apresentar barra de pesquisa que permita vincular à atração usuários já cadastrados no sistema com perfil Editor, Leitor, Agência ou Agente; os perfis Parceiro Comercial e Turista não devem estar disponíveis para vínculo ou cadastro nesta tela.                                                   |
| RF-021.12 | O sistema deve exibir, por usuário, botão que permita reenviar ou resetar a senha (ex.: "Resetar senha").                                                                                                                                                                                                             |
| RF-021.13 | O modal de Novo/Editar usuário deve exibir os campos: foto de perfil, Atração (pré-preenchida e somente leitura no contexto), primeiro nome, último nome, CPF/CNPJ, e-mail de contato, telefone, idioma padrão, senha, data de criação, último acesso, perfil (apenas opções Editor, Leitor, Agência, Agente), ativo. |
| RF-021.14 | Ao criar usuário com perfil Editor ou Leitor no contexto da atração, o sistema deve preencher automaticamente os campos Parceiro Comercial e Atração de acordo com a atração em que o usuário está sendo criado.                                                                                                      |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-021.01 | O sistema deve exibir botão que permita reenviar ou resetar a senha caso o usuário não tenha recebido o e-mail com a senha provisória.                                                                        |
| RN-021.02 | Ao criar usuário Editor ou Leitor no contexto da atração, o sistema deve preencher automaticamente o campo Parceiro Comercial e o campo Atração de acordo com a atração em que está sendo criado.             |
| RN-021.03 | Usuários Leitores vinculados à atração têm acesso às rotinas Validar Ingresso e Pesquisar Ingresso.                                                                                                           |
| RN-021.04 | Usuários Editores vinculados à atração têm acesso às rotinas: Validar Ingresso, Pesquisar Ingresso, Editar Atração, Gestão de Ingresso, Categorias, Gestão de Cupons, Totais da Atração e Gráficos Analytics. |
| RN-021.05 | Nesta tela não é permitido vincular nem cadastrar usuários com perfil Parceiro Comercial ou Turista; o dropdown de perfil deve oferecer apenas Editor, Leitor, Agência e Agente.                              |
| RN-021.06 | A ação "Desvincular" remove o vínculo do usuário com a atração; não exclui o usuário do sistema.                                                                                                              |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                      | Resultado Esperado                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| CA-021.01 | Acessar Detalhes da Atração > Usuários como Administrador ou Parceiro Comercial vinculado à atração                                                                                                           | Tela exibida com aba "Ativos" selecionada e tabela de usuários da atração                            |
| CA-021.02 | Dado que o usuário pesquisa por nome ou e-mail, quando digita na barra de pesquisa, então a lista é filtrada pelos usuários vinculados à atração que atendem ao critério                                      | Lista filtrada exibindo apenas usuários da atração que correspondem à busca                          |
| CA-021.03 | Dado que o usuário clica em "Adicionar usuário", quando o modal abre, então o campo Perfil oferece apenas Editor, Leitor, Agência e Agente                                                                    | Dropdown de Perfil não exibe opções Parceiro Comercial nem Turista                                   |
| CA-021.04 | Dado que um novo usuário é incluído na atração, quando o cadastro é salvo, então o sistema envia senha provisória por e-mail ao endereço informado                                                            | E-mail com senha provisória enviado; usuário consegue primeiro acesso com essa senha                 |
| CA-021.05 | Dado que o usuário clica em "Resetar senha" ou equivalente para um usuário vinculado, quando confirma, então o sistema reenvia ou redefine a senha e comunica por e-mail                                      | Senha reenviada ou resetada; e-mail enviado ao usuário                                               |
| CA-021.06 | Dado que Parceiro Comercial cria usuário Editor ou Leitor na atração, quando o modal é aberto, então os campos Parceiro Comercial e Atração estão preenchidos automaticamente com a atração atual             | Campos Parceiro Comercial e Atração exibem valores corretos e não editáveis no contexto              |
| CA-021.07 | Dado que o usuário aciona "Desvincular" para um usuário da atração, quando confirma, então o vínculo é removido e o usuário deixa de aparecer na lista da atração (o usuário permanece cadastrado no sistema) | Usuário removido da listagem da atração; registro de usuário no sistema mantido                      |
| CA-021.08 | Verificar perfis disponíveis no dropdown ao adicionar usuário nesta tela                                                                                                                                      | Apenas Editor, Leitor, Agência e Agente estão disponíveis; Parceiro Comercial e Turista não aparecem |

Protótipo/Wireframe:

Figura  - WF-026 - Detalhes da Atração/Usuários

**Figura  -WF-026 - Detalhes da Atração/Usuários**

Figura  - WF-027 - Detalhes da Atração/Gestão de usuários/Adicionar usuário

### 3.22 Detalhes da Atrações/Gestão Financeira/Relatórios da Atração- Administrador
