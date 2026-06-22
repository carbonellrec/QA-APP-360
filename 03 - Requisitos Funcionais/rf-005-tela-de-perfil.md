### 3.5 Tela de Perfil

**ID:** RF-005

Módulo: Perfil

Perfis com Acesso: Todos os perfis autenticados

**Prioridade:** Média

**Descrição** : O sistema deve disponibilizar um modal de perfil onde o usuário autenticado pode visualizar e editar suas configurações pessoais. Algumas funcionalidades são exclusivas para perfis específicos (Parceiro Comercial).

Requisitos Detalhados

| ID        | Requisito                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------|
| RF-005.01 | O sistema deve exibir o modal de perfil ao clicar no menu "Perfil" ou no nome/foto do usuário |
| RF-005.02 | O modal deve exibir o título "Perfil" com subtítulo "Gerencie suas configurações de perfil"   |
| RF-005.03 | O modal deve exibir os botões "Sair" (fechar sem salvar) e "Salvar" no cabeçalho              |
| RF-005.04 | O sistema deve validar os campos obrigatórios antes de salvar                                 |
| RF-005.05 | O sistema deve exibir mensagem de sucesso após salvar alterações                              |

Campos do Formulário

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-005.06 | O sistema deve exibir área para  **Foto de Perfil**  com opções "Carregar nova foto" e "Apagar" |
| RF-005.07 | O sistema deve exibir campos  **Primeiro nome**  e  **Último nome**  (editáveis)                |
| RF-005.08 | O sistema deve exibir campo  **CPF/CNPJ**  (somente visualização)                               |
| RF-005.09 | O sistema deve exibir campo  **E-mail de contato**  principal (somente visualização)            |
| RF-005.10 | O sistema deve exibir campo  **Telefone**  (editável)                                           |
| RF-005.11 | O sistema deve exibir campo  **Idioma padrão**  (editável via select)                           |

Funcionalidades Exclusivas - Parceiro Comercial

| ID        | Requisito                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| RF-005.12 | Para perfil  **Parceiro Comercial**  : exibir botão "Adicionar outro email"                          |
| RF-005.13 | Para perfil  **Parceiro Comercial**  : exibir seção "Integração da conta" com opção Google Analytics |
| RF-005.14 | O sistema deve permitir conectar/desconectar conta do Google Analytics                               |

Campos do Formulário - Detalhamento

| Campo             | Tipo     | Editável   | Obrigatório   | Observação                                  |
|-------------------|----------|------------|---------------|---------------------------------------------|
| Foto de Perfil    | Upload   | ✅          | ❌             | PNG, JPEG - máx 5MB                         |
| Primeiro nome     | Texto    | ✅          | ✅             | Máximo 50 caracteres                        |
| Último nome       | Texto    | ✅          | ✅             | Máximo 50 caracteres                        |
| CPF/CNPJ          | Texto    | ❌          | -             | Apenas visualização                         |
| E-mail principal  | E-mail   | ❌          | -             | Apenas visualização (usado no login)        |
| E-mail secundário | E-mail   | ✅          | ❌             | Apenas Parceiro Comercial, máx 1 adicional  |
| Telefone          | Telefone | ✅          | ✅             | Formato (XX) XXXXX-XXXX                     |
| Idioma padrão     | Select   | ✅          | ✅             | Português Brasil (padrão), Inglês, Espanhol |

Seção: Integração da Conta (Apenas Parceiro Comercial)

| Campo            | Descrição                                                                                                           |
|------------------|---------------------------------------------------------------------------------------------------------------------|
| Google Analytics | Permite ao Parceiro Comercial conectar sua conta do Google Analytics para monitorar acessos à página de sua atração |
| Status           | "Conectado" ou "Desconectado"                                                                                       |
| Ação             | Botão para conectar/desconectar                                                                                     |

Regras de Negócio

| ID        | Regra                                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------------------|
| RN-005.01 | O campo  **E-mail principal**  (primeiro e-mail cadastrado) não pode ser alterado pelo usuário                 |
| RN-005.02 | O campo  **CPF/CNPJ**  não pode ser alterado pelo usuário (somente via Gestão de Usuários)                     |
| RN-005.03 | O campo  **Perfil**  não pode ser alterado pelo usuário (somente via Gestão de Usuários)                       |
| RN-005.04 | O usuário  **não pode**  alterar ou resetar sua senha por este modal - deve solicitar ao suporte da plataforma |
| RN-005.05 | A foto deve ter tamanho máximo de  **5MB**  e formatos aceitos: PNG, JPEG                                      |
| RN-005.06 | Ao clicar em "Apagar" na foto, o sistema remove a foto atual e exibe o avatar padrão                           |
| RN-005.07 | O telefone deve ser validado no formato brasileiro: (XX) XXXXX-XXXX                                            |
| RN-005.08 | O  **Idioma padrão**  afeta a interface do backoffice E os e-mails enviados ao usuário                         |
| RN-005.09 | O idioma padrão é  **Português Brasil**  para novos usuários                                                   |
| RN-005.10 | Apenas o perfil  **Parceiro Comercial**  pode adicionar e-mail secundário                                      |
| RN-005.11 | O limite máximo de e-mails é  **2**  (1 principal + 1 secundário)                                              |
| RN-005.12 | Apenas o perfil  **Parceiro Comercial**  visualiza a seção "Integração da conta"                               |
| RN-005.13 | A integração com Google Analytics permite ao Parceiro Comercial monitorar acessos à página de sua atração      |

Critérios de Aceitação

| ID        | Critério                                       | Resultado Esperado                                                        |
|-----------|------------------------------------------------|---------------------------------------------------------------------------|
| CA-005.01 | Clicar em "Perfil" no menu                     | Modal de perfil é aberto                                                  |
| CA-005.02 | Visualizar dados do perfil                     | Campos exibem dados corretos do usuário logado                            |
| CA-005.03 | Editar Primeiro nome e Último nome             | Campos são editáveis e salvos corretamente                                |
| CA-005.04 | Tentar editar CPF/CNPJ                         | Campo é exibido como somente leitura                                      |
| CA-005.05 | Tentar editar e-mail principal                 | Campo é exibido como somente leitura                                      |
| CA-005.06 | Fazer upload de foto válida (PNG, 3MB)         | Foto é carregada e exibida                                                |
| CA-005.07 | Fazer upload de foto > 5MB                     | Mensagem "Arquivo excede o tamanho máximo de 5MB"                         |
| CA-005.08 | Fazer upload de arquivo não suportado (PDF)    | Mensagem "Formato não suportado. Use PNG ou JPEG"                         |
| CA-005.09 | Clicar em "Apagar" na foto                     | Foto removida, avatar padrão exibido                                      |
| CA-005.10 | Alterar idioma para "Inglês"                   | Interface atualiza para inglês após salvar                                |
| CA-005.11 | Clicar em "Sair"                               | Modal fechado, alterações descartadas                                     |
| CA-005.12 | Clicar em "Salvar" com dados válidos           | Dados salvos + mensagem "Perfil atualizado com sucesso"                   |
| CA-005.13 | Acessar perfil como  **Parceiro Comercial**    | Seções "Adicionar outro email" e "Integração da conta" visíveis           |
| CA-005.14 | Acessar perfil como  **Administrador**         | Seções "Adicionar outro email" e "Integração da conta"  **não**  visíveis |
| CA-005.15 | Parceiro Comercial adiciona e-mail secundário  | E-mail adicionado com sucesso (limite 2)                                  |
| CA-005.16 | Parceiro Comercial tenta adicionar 3º e-mail   | Botão "Adicionar outro email" desabilitado/oculto                         |
| CA-005.17 | Parceiro Comercial conecta Google Analytics    | Status muda para "Conectado"                                              |
| CA-005.18 | Parceiro Comercial desconecta Google Analytics | Status muda para "Desconectado"                                           |

Protótipo/Wireframe

Figura  - WF-004 - Perfil

### 3.6 Gestão de Usuários - Administrador
