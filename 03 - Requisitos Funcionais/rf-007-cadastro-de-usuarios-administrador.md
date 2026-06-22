### 3.7 Cadastro de Usuários - Administrador

**ID:** RF-007

Módulo: Gestão de Usuários &gt; Cadastro/Edição

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador cadastre novos usuários ou edite/visualize usuários existentes através de um modal. Os campos exibidos variam dinamicamente conforme o perfil selecionado. O mesmo modal é utilizado para as três ações: Novo, Editar e Visualizar.

**Requisitos Detalhados**

**Estrutura Geral do Modal**

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-007.01 | O sistema deve exibir modal com título "Novo/Editar Usuário"                                |
| RF-007.02 | O sistema deve exibir subtítulo "Preencha os campos obrigatórios para adicionar um usuário" |
| RF-007.03 | O sistema deve exibir botões "Descartar" e "Salvar" no cabeçalho                            |
| RF-007.04 | O sistema deve validar campos obrigatórios antes de salvar                                  |
| RF-007.05 | O sistema deve exibir campos específicos dinamicamente conforme o perfil selecionado        |

**Modos de Operação**

| Modo         | Descrição                      | Campos de Senha                     | Data Criação   | Último Acesso   | Campos        |
|--------------|--------------------------------|-------------------------------------|----------------|-----------------|---------------|
| Novo         | Cadastro de novo usuário       | ❌ Oculto                            | Data atual     | Em branco ("-") | Habilitados   |
| Edição       | Alteração de usuário existente | ✅ Visível (criptografado + Resetar) | Preenchido     | Preenchido      | Habilitados   |
| Visualização | Consulta de usuário            | ✅ Visível (criptografado)           | Preenchido     | Preenchido      | Desabilitados |

**Campos Comuns (Todos os Perfis)**

| Campo               | Tipo      | Obrigatório   | Editável   | Observação                                                                  |
|---------------------|-----------|---------------|------------|-----------------------------------------------------------------------------|
| Foto de Perfil      | Upload    | ❌             | ✅          | PNG, JPEG - máx 5MB                                                         |
| Primeiro nome       | Texto     | ✅             | ✅          | Máximo 50 caracteres                                                        |
| Último nome         | Texto     | ✅             | ✅          | Máximo 50 caracteres                                                        |
| CPF/CNPJ            | Texto     | ❌             | ✅          | Máscara automática                                                          |
| Email de contato    | E-mail    | ✅             | ✅          | Permite adicionar outro email (máx 2)                                       |
| Telefone            | Telefone  | ✅             | ✅          | Formato (XX) XXXXX-XXXX                                                     |
| Idioma padrão       | Select    | ✅             | ✅          | Português Brasil (padrão), Inglês, Espanhol                                 |
| Senha               | Password  | -             | ❌          | Apenas visualização (criptografado) - só no modo Edição/Visualização        |
| Botão Resetar Senha | Botão     | -             | -          | Apenas no modo Edição                                                       |
| Data de criação     | Data/Hora | -             | ❌          | Somente leitura - Data atual no modo Novo                                   |
| Último acesso       | Data/Hora | -             | ❌          | Somente leitura - Em branco ("-") no modo Novo                              |
| Perfil              | Select    | ✅             | ✅          | Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente, Turista |
| Ativo               | Toggle    | ✅             | ✅          | Ativar/desativar o usuário                                                  |

**Campos Específicos por Perfil**

**Perfil: Parceiro Comercial**

| Seção            | Campo              | Tipo           | Obrigatório   | Observação                                              |
|------------------|--------------------|----------------|---------------|---------------------------------------------------------|
| Gestor           | Nome               | Texto          | ✅             | Primeiro nome do gestor                                 |
| Gestor           | Último nome        | Texto          | ✅             | Último nome do gestor                                   |
| Gestor           | Email do Gestor    | E-mail         | ✅             | Permite adicionar outro email (máx 2)                   |
| Gestor           | Telefone do Gestor | Telefone       | ✅             | Formato (XX) XXXXX-XXXX                                 |
| Dados da empresa | Razão Social       | Texto          | ✅             | Nome legal da empresa                                   |
| Dados da empresa | Nome Fantasia      | Texto          | ✅             | Nome comercial                                          |
| Dados da empresa | CNPJ               | Texto          | ✅             | Máscara  [XX.XXX.XXX/XXXX-XX](http:/XX.XXX.XXX/XXXX-XX) |
| Dados da empresa | Inscrição Estadual | Texto + Toggle | ✅             | Campo texto OU marcar "Isento"                          |
| Integração       | Google Analytics   | Botão          | ❌             | Conectar/Desconectar conta do GA                        |

**Perfil: Editor / Leitor**

| Campo              | Tipo                      | Obrigatório   | Observação                                                                                       |
|--------------------|---------------------------|---------------|--------------------------------------------------------------------------------------------------|
| Parceiro Comercial | Select com pesquisa       | ✅             | Pesquisa por nome do Parceiro Comercial                                                          |
| Atração            | Multi-select com pesquisa | ✅             | Exibe atrações ativas do Parceiro selecionado. Pesquisa por nome ou ID. Permite múltipla seleção |

**Perfil: Agência**

| Campo              | Tipo                      | Obrigatório   | Observação                                                             |
|--------------------|---------------------------|---------------|------------------------------------------------------------------------|
| Visibilidade       | Select                    | ✅             | Opções: "Pública" ou "Reservada"                                       |
| Parceiro Comercial | Multi-select com pesquisa | Condicional   | Visível apenas se Visibilidade = "Reservada". Permite múltipla seleção |
| Atração            | Multi-select com pesquisa | ❌             | Permite vincular a múltiplas atrações. Pesquisa por nome ou ID         |

**Perfil: Agente**

| Campo   | Tipo                | Obrigatório   | Observação                                                                |
|---------|---------------------|---------------|---------------------------------------------------------------------------|
| Agência | Select com pesquisa | ❌             | Pesquisa por nome ou ID da agência. Pode ser independente (não vinculado) |

**Perfil: Turista**

| Campo       | Tipo   | Obrigatório   | Observação                                  |
|-------------|--------|---------------|---------------------------------------------|
| Estrangeiro | Toggle | ✅             | Sim/Não - Indica se o turista é estrangeiro |

**Regras de Negócio**

| ID        | Regra                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------|
| RN-007.01 | O campo ID é gerado automaticamente de forma incremental ao salvar                               |
| RN-007.02 | O ID só é exibido na tela de Gestão de Usuários após salvar (não aparece no modal de cadastro)   |
| RN-007.03 | Ao cadastrar novo usuário, o sistema gera senha provisória automaticamente                       |
| RN-007.04 | A senha provisória é enviada via e-mail E SMS para o usuário                                     |
| RN-007.05 | O botão "Resetar senha" gera nova senha provisória e envia por e-mail e SMS                      |
| RN-007.06 | O Administrador não pode definir ou visualizar a senha do usuário (apenas resetar)               |
| RN-007.07 | A foto de perfil deve ter tamanho máximo de 5MB e formatos PNG ou JPEG                           |
| RN-007.08 | O e-mail principal (primeiro cadastrado) é usado para login e não pode ser alterado após criação |
| RN-007.09 | O limite máximo de e-mails é 2 (1 principal + 1 secundário)                                      |
| RN-007.10 | O campo Idioma padrão define o idioma da interface E dos e-mails enviados ao usuário             |
| RN-007.11 | Para Editor/Leitor: o campo "Atração" só exibe atrações ativas do Parceiro Comercial selecionado |
| RN-007.12 | Para Agência Pública: pode ser vinculada a múltiplos Parceiros Comerciais e Atrações             |
| RN-007.13 | Para Agência Reservada: o campo "Parceiro Comercial" é obrigatório e visível                     |
| RN-007.14 | Para Agente: o campo "Agência" permite pesquisa por nome ou ID                                   |
| RN-007.15 | O perfil Turista pode ser cadastrado pelo Admin ou via auto-cadastro no portal público           |
| RN-007.16 | No modo Visualização, todos os campos devem estar desabilitados (somente leitura)                |
| RN-007.17 | O campo "Data de criação" exibe a data atual automaticamente no cadastro de novo usuário         |
| RN-007.18 | O campo "Último acesso" exibe "-" (em branco) para usuários que nunca logaram                    |
| RN-007.19 | Campos de Gestor, Dados da empresa e Integração são exclusivos do perfil Parceiro Comercial      |
| RN-007.20 | Para Parceiro Comercial cadastrado manualmente pelo Administrador via este modal, o parceiro é criado diretamente com status "Ativa", sem passar pela fila de aprovação do módulo de Gestão de Parceiros Comerciais (RF-057). Os Contratos de Atração devem ser gerados pelo Admin via botão "Adicionar Contrato" em RF-008 quando as atrações forem cadastradas. |

**Validações**

| Campo              | Validação                                                        |
|--------------------|------------------------------------------------------------------|
| E-mail             | Formato válido, único no sistema (case insensitive)              |
| Telefone           | Formato brasileiro (XX) XXXXX-XXXX                               |
| CPF                | 11 dígitos, validação de dígitos verificadores                   |
| CNPJ               | 14 dígitos, validação de dígitos verificadores, único no sistema |
| Foto               | Máximo 5MB, formatos PNG ou JPEG                                 |
| Inscrição Estadual | Texto ou marcado como "Isento"                                   |

Critérios de Aceitação

**Modo Novo (Cadastro)**

| ID        | Critério                                            | Resultado Esperado                                          |
|-----------|-----------------------------------------------------|-------------------------------------------------------------|
| CA-007.01 | Clicar em "Adicionar usuário" na Gestão de Usuários | Modal abre em modo Novo                                     |
| CA-007.02 | Verificar seção de Senha no modo Novo               | Seção de senha não aparece                                  |
| CA-007.03 | Verificar Data de criação                           | Exibe data/hora atual                                       |
| CA-007.04 | Verificar Último acesso                             | Exibe "-" (em branco)                                       |
| CA-007.05 | Preencher campos obrigatórios e salvar              | Usuário criado + e-mail e SMS enviados com senha provisória |
| CA-007.06 | Verificar ID após salvar                            | ID não aparece no modal, mas aparece na listagem            |

**Modo Edição**

| ID        | Critério                                | Resultado Esperado                                  |
|-----------|-----------------------------------------|-----------------------------------------------------|
| CA-007.07 | Selecionar usuário e clicar em "Editar" | Modal abre em modo Edição com campos habilitados    |
| CA-007.08 | Verificar seção de Senha                | Senha aparece criptografada + botão "Resetar senha" |
| CA-007.09 | Clicar em "Resetar senha"               | Confirmação + nova senha enviada por e-mail e SMS   |
| CA-007.10 | Alterar dados e salvar                  | Dados atualizados + mensagem de sucesso             |

**Modo Visualização**

| ID        | Critério                                    | Resultado Esperado                              |
|-----------|---------------------------------------------|-------------------------------------------------|
| CA-007.11 | Clicar em linha da tabela (não no checkbox) | Modal abre em modo Visualização                 |
| CA-007.12 | Verificar campos                            | Todos os campos desabilitados (somente leitura) |
| CA-007.13 | Verificar botão "Resetar senha"             | Botão não aparece no modo visualização          |

**Campos Dinâmicos por Perfil**

| ID        | Critério                                      | Resultado Esperado                                    |
|-----------|-----------------------------------------------|-------------------------------------------------------|
| CA-007.14 | Selecionar perfil "Administrador"             | Apenas campos comuns são exibidos                     |
| CA-007.15 | Selecionar perfil "Parceiro Comercial"        | Seções Gestor, Dados da empresa e Integração aparecem |
| CA-007.16 | Selecionar perfil "Editor" ou "Leitor"        | Campos Parceiro Comercial e Atração aparecem          |
| CA-007.17 | Selecionar Parceiro Comercial (Editor/Leitor) | Campo Atração exibe apenas atrações deste Parceiro    |
| CA-007.18 | Selecionar perfil "Agência"                   | Campos Visibilidade e Atração aparecem                |
| CA-007.19 | Selecionar Visibilidade "Reservada" (Agência) | Campo Parceiro Comercial aparece                      |
| CA-007.20 | Selecionar Visibilidade "Pública" (Agência)   | Campo Parceiro Comercial não aparece                  |
| CA-007.21 | Selecionar perfil "Agente"                    | Campo Agência aparece                                 |
| CA-007.22 | Selecionar perfil "Turista"                   | Campo Estrangeiro aparece                             |

**Validações**

| ID        | Critério                                 | Resultado Esperado                                |
|-----------|------------------------------------------|---------------------------------------------------|
| CA-007.23 | Salvar sem preencher campos obrigatórios | Mensagem de erro indicando campos faltantes       |
| CA-007.24 | Cadastrar e-mail já existente            | Mensagem "E-mail já cadastrado no sistema"        |
| CA-007.25 | Cadastrar CNPJ já existente              | Mensagem "CNPJ já cadastrado no sistema"          |
| CA-007.26 | Upload de foto > 5MB                     | Mensagem "Arquivo excede o tamanho máximo de 5MB" |
| CA-007.27 | Upload de arquivo não suportado          | Mensagem "Formato não suportado. Use PNG ou JPEG" |

**Protótipo/Wireframe**

Figura  - WF-006 - Adicionar Usuários.png

### 3.8 Tela Gestão de Contratos - Administrador
