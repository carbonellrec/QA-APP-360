### 3.1 Autenticação com E-mail e Senha

**ID:** RF-001

Módulo: Autenticação

Perfis com Acesso: Todos (Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente)

**Prioridade:** Alta (Essencial)

Descrição: O sistema deve permitir que usuários cadastrados realizem autenticação utilizando e-mail e senha para acessar as funcionalidades do Backoffice.

**Requisitos Detalhados**

| ID        | Requisito                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------------------------|
| RF-001.01 | O sistema deve exibir uma tela de login com os campos: E-mail e Senha                                          |
| RF-001.02 | O sistema deve validar as credenciais informadas contra a base de dados                                        |
| RF-001.03 | O sistema deve exibir mensagem de erro genérica em caso de credenciais inválidas                               |
| RF-001.04 | O sistema deve redirecionar o usuário para a tela inicial correspondente ao seu perfil após login bem-sucedido |
| RF-001.05 | O sistema deve disponibilizar a opção "Esqueci minha senha"                                                    |
| RF-001.06 | O sistema deve bloquear a conta após 5 tentativas inválidas consecutivas                                       |
| RF-001.07 | O sistema deve manter a sessão ativa por 8 horas de inatividade                                                |
| RF-001.08 | O sistema deve permitir que o usuário realize logout a qualquer momento                                        |
| RF-001.09 | O sistema deve permitir que o usuário realize a criação da conta ou login com Google ou Facebook               |

**Regras de Negócio**

| ID        | Regra                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------|
| RN-001.01 | A mensagem de erro deve ser genérica: "E-mail ou senha inválidos" (não informar qual campo está errado por segurança) |
| RN-001.02 | A senha deve ter no mínimo 8 caracteres, contendo letras maiúsculas, minúsculas e números                             |
| RN-001.03 | O e-mail deve ser único no sistema (não permitir duplicidade)                                                         |
| RN-001.04 | Usuários inativos não podem realizar login                                                                            |
| RN-001.05 | Após bloqueio por tentativas inválidas, o desbloqueio deve ser feito pelo Administrador                               |
| RN-001.06 | Ao solicitar recuperação de senha, o sistema deve enviar uma senha provisória por e-mail                              |
| RN-001.07 | Ao fazer login com senha provisória, o sistema deve obrigar a troca de senha                                          |

Critérios de Aceitação

| ID        | Critério                             | Resultado Esperado                                                                 |
|-----------|--------------------------------------|------------------------------------------------------------------------------------|
| CA-001.01 | Login com credenciais válidas        | Usuário é redirecionado para a tela inicial do seu perfil                          |
| CA-001.02 | Login com e-mail inválido            | Mensagem "E-mail ou senha inválidos"                                               |
| CA-001.03 | Login com senha inválida             | Mensagem "E-mail ou senha inválidos"                                               |
| CA-001.04 | Login com usuário inativo            | Mensagem "Usuário inativo. Entre em contato com o administrador"                   |
| CA-001.05 | 5 tentativas inválidas consecutivas  | Conta bloqueada + mensagem "Conta bloqueada. Entre em contato com o administrador" |
| CA-001.06 | Solicitar recuperação de senha       | E-mail enviado com senha provisória em até 5 minutos                               |
| CA-001.07 | Login com senha provisória           | Sistema exibe tela obrigatória de troca de senha                                   |
| CA-001.08 | Sessão expira após 8h de inatividade | Usuário é redirecionado para tela de login                                         |

**Protótipo/Wireframe**

Figura  WF-001 - Tela de login.png

### 3.2 Tela Inicial
