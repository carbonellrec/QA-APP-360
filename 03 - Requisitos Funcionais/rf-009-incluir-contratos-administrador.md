### 3.9 Incluir Contratos - Administrador

**ID:** RF-009

Módulo: Gestão de Contratos &gt; Cadastro/Edição

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador crie e edite contratos. A tela apresenta uma pré-visualização do contrato à esquerda com campos editáveis inline, sincronizados com o painel de preenchimento à direita. O tipo de contrato (template) é carregado automaticamente conforme o perfil do usuário selecionado.

**Requisitos Detalhados**

**Estrutura da Tela**

| ID        | Requisito                                                                                                          |
|-----------|--------------------------------------------------------------------------------------------------------------------|
| RF-009.01 | O sistema deve exibir título "Gestão de Contratos" com subtítulo "Gerencie os contratos do sistema"                |
| RF-009.02 | O sistema deve exibir barra de progresso indicando o percentual de campos preenchidos                              |
| RF-009.03 | O sistema deve exibir botões "Preview" e "Salvar" no cabeçalho                                                     |
| RF-009.04 | O sistema deve dividir a tela em duas colunas: Template do contrato (esquerda) e Painel de preenchimento (direita) |

**Cabeçalho do Formulário**

| Campo               | Tipo             | Obrigatório   | Descrição                                           |
|---------------------|------------------|---------------|-----------------------------------------------------|
| Parceiro ou Agência | Select com busca | ✅             | Seleciona o usuário (Parceiro Comercial ou Agência) |
| ID do contrato      | Somente leitura  | -             | Gerado automaticamente após salvar                  |

**Tipos de Contrato**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.05 | Ao selecionar um usuário Parceiro Comercial, o sistema carrega o template de Contrato de Atração |
| RF-009.06 | Ao selecionar um usuário Agência, o sistema carrega o template de Contrato de Agência            |
| RF-009.07 | Cada tipo de contrato possui um template diferente (fornecido pelo cliente)                      |

| Tipo                | Usuário            | Template                    | Vinculação         |
|---------------------|--------------------|-----------------------------|--------------------|
| Contrato de Atração | Parceiro Comercial | Template Parceiro Comercial | Atração específica |
| Contrato de Agência | Agência            | Template Agência            | Agência            |

Seleção de Atração (apenas para Contrato de Atração)

| ID         | Requisito                                                                                                                                                                  |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-009.07A | Após selecionar um Parceiro Comercial, o sistema deve exibir o campo "Selecionar Atração"                                                                                  |
| RF-009.07B | O campo "Selecionar Atração" deve listar apenas atrações do Parceiro selecionado com status "Pendente de Contrato" ou "Rascunho"                                           |
| RF-009.07C | O campo deve ser do tipo select com busca, permitindo pesquisa por ID ou Nome da atração                                                                                   |
| RF-009.07D | Se o Parceiro não tiver atrações disponíveis, exibir mensagem: "Este parceiro não possui atrações disponíveis para vinculação de contrato. Cadastre uma atração primeiro." |
| RF-009.07E | Uma atração só pode ter um contrato ativo por vez. Se já existir contrato ativo para a atração, ela não deve aparecer na lista                                             |
| RF-009.07F | Após a assinatura do contrato no Docusign, a atração vinculada deve ter seu status alterado automaticamente para "Ativo"                                                   |
| RF-009.07G | O campo "Selecionar Atração" NÃO aparece para contratos de Agência (apenas para Contrato de Atração)                                                                       |

**Coluna Esquerda - Template do Contrato**

| ID        | Requisito                                                                                |
|-----------|------------------------------------------------------------------------------------------|
| RF-009.08 | O sistema deve exibir o template fixo do contrato com campos editáveis inline            |
| RF-009.09 | Os campos editáveis são numerados (1, 2, 3...) para facilitar identificação              |
| RF-009.10 | Os campos inline são sincronizados com os campos do painel à direita                     |
| RF-009.11 | Ao preencher um campo no painel direito, o valor é refletido automaticamente no template |
| RF-009.12 | O template é somente leitura (admin não pode editar o texto, apenas os campos)           |

**Coluna Direita - Painel de Preenchimento**

O painel possui duas abas:

**Aba 1: Informações do Contrato**

| ID        | Requisito                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------|
| RF-009.13 | Ao selecionar o Parceiro/Agência, os campos são preenchidos automaticamente com dados do cadastro |
| RF-009.14 | Os campos preenchidos automaticamente são editáveis pelo admin                                    |
| RF-009.15 | Os campos específicos serão definidos quando o cliente fornecer o template                        |

Nota: Os campos definitivos serão documentados após recebimento do template do cliente.

**Aba 2: Condições**

| Seção                   | Descrição                                       |
|-------------------------|-------------------------------------------------|
| Condições Comerciais    | Vincula condições cadastradas no módulo RF 3.10 |
| Informações Financeiras | Define parâmetros de repasse financeiro         |
| Informações Adicionais  | Campo de texto livre                            |

**Seção: Condições Comerciais**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-009.16 | O sistema deve exibir select para escolher Condições Comerciais cadastradas (RF-010) |
| RF-009.17 | O sistema deve permitir criar condições (botão "Criar condição")                     |
| RF-009.18 | O botão "Criar condição" deve abrir o modal de nova condição comercial RF 3.10       |

**Seção: Informações Financeiras**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.19 | O sistema deve permitir criar informações financeiras (botão "Criar informação financeira")      |
| RF-009.20 | O botão " Criar informação financeira " deve abrir o modal de nova informação financeira RF 3.10 |

**Seção: Informações Adicionais**

| ID        | Requisito                                                                               |
|-----------|-----------------------------------------------------------------------------------------|
| RF-009.21 | O sistema deve exibir campo de texto livre para informações adicionais                  |
| RF-009.22 | O conteúdo deste campo é inserido no corpo do contrato ao final dos campos estruturados |

**Barra de Progresso**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.23 | O sistema deve exibir barra de progresso indicando percentual de campos obrigatórios preenchidos |
| RF-009.24 | A barra deve atualizar em tempo real conforme os campos são preenchidos                          |
| RF-009.25 | O sistema deve indicar visualmente quando todos os campos obrigatórios estão preenchidos (100%)  |

**Funcionalidades dos Botões**

**Botão Preview**

| ID        | Requisito                                                                      |
|-----------|--------------------------------------------------------------------------------|
| RF-009.26 | Ao clicar em "Preview", o sistema gera e baixa o PDF do contrato               |
| RF-009.27 | O PDF é gerado com as informações preenchidas até o momento (mesmo incompleto) |
| RF-009.28 | Campos não preenchidos aparecem em branco ou com placeholder no PDF            |

**Botão Salvar**

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-009.29 | Ao clicar em "Salvar", o sistema verifica se todos os campos obrigatórios estão preenchidos |
| RF-009.30 | Se incompleto: exibe modal de confirmação (ver fluxo abaixo)                                |
| RF-009.31 | Se completo: salva com status "Aguardando Envio"                                            |

**Modos de Operação**

| Modo         | Descrição                 | Campos        | Botões          | Origem                                    |
|--------------|---------------------------|---------------|-----------------|-------------------------------------------|
| Novo         | Criar novo contrato       | Habilitados   | Preview, Salvar | Botão "Adicionar Contrato" (RF-008)       |
| Edição       | Editar contrato existente | Habilitados   | Preview, Salvar | Selecionar 1 contrato + "Editar" (RF-008) |
| Visualização | Consultar contrato        | Desabilitados | Preview         | Clicar na linha do contrato (RF-008)      |

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-009.32 | No modo Visualização, todos os campos devem estar desabilitados (somente leitura)           |
| RF-009.33 | No modo Visualização, o botão "Salvar" não é exibido                                        |
| RF-009.34 | Contratos com status "Ativo", "Enviado a Docusign" ou "Expirado" abrem em modo Visualização |
| RF-009.35 | Contratos com status "Rascunho" ou "Aguardando Envio" abrem em modo Edição                  |

**Regras de Negócio**

| ID        | Regra                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------|
| RN-009.01 | O ID do contrato é gerado automaticamente de forma incremental ao salvar                         |
| RN-009.02 | O ID só é exibido após o primeiro salvamento                                                     |
| RN-009.03 | O template do contrato é fixo e fornecido pelo cliente (admin não pode editar o texto)           |
| RN-009.04 | Ao selecionar Parceiro Comercial, carrega template de Contrato de Atração                        |
| RN-009.05 | Ao selecionar Agência, carrega template de Contrato de Agência                                   |
| RN-009.06 | Campos do cadastro (Razão Social, CNPJ, Endereço) são preenchidos automaticamente, mas editáveis |
| RN-009.07 | Os campos inline no template são sincronizados com o painel de preenchimento                     |
| RN-009.08 | A barra de progresso calcula: (campos preenchidos / campos obrigatórios) × 100%                  |
| RN-009.09 | Contrato salvo com campos faltantes recebe status "Rascunho"                                     |
| RN-009.10 | Contrato salvo com todos os campos preenchidos recebe status "Aguardando Envio"                  |
| RN-009.11 | Contratos "Rascunho" não podem ser enviados para Docusign                                        |
| RN-009.12 | O botão "Preview" gera PDF mesmo com campos incompletos                                          |
| RN-009.13 | O campo "Informações Adicionais" é texto livre inserido ao final do corpo do contrato            |
| RN-009.14 | As Condições Comerciais vinculadas devem estar cadastradas no módulo RF-010                      |
| RN-009.15 | Múltiplas Condições Comerciais e Informações Financeiras podem ser adicionadas a um contrato     |

Critérios de Aceitação

**Abertura e Carregamento**

| ID        | Critério                                              | Resultado Esperado                                    |
|-----------|-------------------------------------------------------|-------------------------------------------------------|
| CA-009.01 | Clicar em "Adicionar Contrato" na Gestão de Contratos | Tela abre em modo Novo (campos vazios)                |
| CA-009.02 | Selecionar 1 contrato "Rascunho" e clicar em "Editar" | Tela abre em modo Edição com dados carregados         |
| CA-009.03 | Clicar na linha de um contrato "Ativo"                | Tela abre em modo Visualização (campos desabilitados) |

**Seleção de Tipo de Contrato**

| ID        | Critério                              | Resultado Esperado                                              |
|-----------|---------------------------------------|-----------------------------------------------------------------|
| CA-009.04 | Selecionar usuário Parceiro Comercial | Template de Contrato de Atração é carregado                     |
| CA-009.05 | Selecionar usuário Agência            | Template de Contrato de Agência é carregado                     |
| CA-009.06 | Selecionar Parceiro Comercial         | Campos Razão Social, CNPJ, Endereço preenchidos automaticamente |

**Preenchimento de Campos**

| ID        | Critério                                | Resultado Esperado                                     |
|-----------|-----------------------------------------|--------------------------------------------------------|
| CA-009.07 | Preencher campo no painel direito       | Valor refletido automaticamente no template à esquerda |
| CA-009.08 | Preencher todos os campos obrigatórios  | Barra de progresso atinge 100%                         |
| CA-009.09 | Editar campo preenchido automaticamente | Campo aceita edição                                    |

**Condições e Informações Financeiras**

| ID        | Critério                                    | Resultado Esperado                             |
|-----------|---------------------------------------------|------------------------------------------------|
| CA-009.10 | Clicar em "Criar condição"                  | Novo select de Condição Comercial é adicionado |
| CA-009.11 | Clicar em "Adicionar informação financeira" | Novo bloco de campos financeiros é adicionado  |
| CA-009.12 | Selecionar Condição Comercial               | Condição vinculada ao contrato                 |

**Preview**

| ID        | Critério                                   | Resultado Esperado                                 |
|-----------|--------------------------------------------|----------------------------------------------------|
| CA-009.13 | Clicar em "Preview" com campos incompletos | PDF é baixado com campos preenchidos até o momento |
| CA-009.14 | Clicar em "Preview" com todos os campos    | PDF completo é baixado                             |

**Salvamento**

| ID        | Critério                                           | Resultado Esperado                           |
|-----------|----------------------------------------------------|----------------------------------------------|
| CA-009.15 | Clicar em "Salvar" com campos incompletos          | Modal de confirmação é exibido               |
| CA-009.16 | Confirmar "Salvar como Rascunho"                   | Contrato salvo com status "Rascunho"         |
| CA-009.17 | Clicar em "Continuar Editando" no modal            | Modal fecha e usuário continua editando      |
| CA-009.18 | Clicar em "Salvar" com todos os campos preenchidos | Contrato salvo com status "Aguardando Envio" |
| CA-009.19 | Salvar novo contrato                               | ID é gerado automaticamente                  |

**Modo Visualização**

| ID        | Critério                                      | Resultado Esperado                  |
|-----------|-----------------------------------------------|-------------------------------------|
| CA-009.20 | Abrir contrato "Ativo"                        | Todos os campos estão desabilitados |
| CA-009.21 | Verificar botão "Salvar" em modo Visualização | Botão não é exibido                 |
| CA-009.22 | Clicar em "Preview" em modo Visualização      | PDF do contrato é baixado           |

**Protótipo/Wireframe**

Figura  - WF-008 - Gestão de contratos/adicionar contrato.png

Pendências

| Item                                | Descrição                           |
|-------------------------------------|-------------------------------------|
| emplate Contrato Parceiro Comercial | Cliente deve fornecer modelo        |
| Template Contrato Agência           | Cliente deve fornecer modelo        |
| Campos específicos do template      | Serão documentados após recebimento |

### 3.10 Configuração Comerciais - Administrador
