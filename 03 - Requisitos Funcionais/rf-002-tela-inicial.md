### 3.2 Tela Inicial

**ID:** RF-002

**Módulo:** Home

**Perfis com Acesso:** Todos os perfis autenticados

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve exibir uma tela inicial personalizada de acordo com o perfil do usuário logado, apresentando o menu de navegação lateral com as opções disponíveis para cada perfil e informações contextuais.

Requisitos Detalhados

| ID        | Requisito                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------|
| RF-002.01 | O sistema deve exibir um menu lateral com as opções de navegação conforme o perfil do usuário |
| RF-002.02 | O sistema deve exibir o nome do usuário logado no cabeçalho                                   |
| RF-002.03 | O sistema deve exibir a foto do usuário (se cadastrada) ou um avatar padrão                   |
| RF-002.04 | O sistema deve disponibilizar um botão de "Sair" (logout) no cabeçalho                        |
| RF-002.05 | O sistema deve exibir um pop-up de confirmação ao clicar em "Sair"                            |
| RF-002.06 | O sistema deve permitir recolher/expandir o menu lateral                                      |

Regras de Negócio

| ID        | Regra                                                                                                                                                                         |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-002.01 | O menu deve exibir apenas as opções disponíveis para o perfil do usuário logado                                                                                               |
| RN-002.02 | O perfil  **Administrador**  deve visualizar: Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| RN-002.03 | Os perfis **Parceiro Comercial, Editor, Leitor, Agência e Agente** têm suas telas iniciais, menus disponíveis e regras de navegação definidos em **RF-056** (Tela Inicial por Perfil — Backoffice). |
| RN-002.04 | O sistema deve destacar visualmente o menu ativo/selecionado                                                                                                                  |

Menus por Perfil (Versão 1.0)

| Perfil             | Menus Disponíveis                                                                                                               |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Administrador      | Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| Parceiro Comercial | Definido na v2.0                                                                                                                |
| Editor             | Definido na v2.0                                                                                                                |
| Leitor             | Definido na v2.0                                                                                                                |
| Agência            | Definido na v2.0                                                                                                                |
| Agente             | Definido na v2.0                                                                                                                |

Critérios de Aceitação

| ID        | Critério                         | Resultado Esperado                                                                                                                          |
|-----------|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| CA-002.01 | Login como Administrador         | Menu exibe: Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| CA-002.02 | Clicar em "Sair"                 | Pop-up de confirmação "Deseja realmente sair?" com opções "Sim" e "Não"                                                                     |
| CA-002.03 | Confirmar logout                 | Usuário redirecionado para tela de login e sessão encerrada                                                                                 |
| CA-002.04 | Cancelar logout                  | Pop-up fechado e usuário permanece logado                                                                                                   |
| CA-002.05 | Verificar nome e foto do usuário | Nome e foto (ou avatar) exibidos corretamente no cabeçalho                                                                                  |

Protótipo/Wireframe

Figura  - WF-002 - Dashboard

### 3.3 Dashboard – Administrador
