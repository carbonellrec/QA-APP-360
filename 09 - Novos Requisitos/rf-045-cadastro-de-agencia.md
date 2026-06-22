### 3.45 Cadastro de Agência

**ID:** RF-045

Módulo: Gestão de Agências > Cadastro/Edição

Perfis com Acesso: Administrador (cadastro manual no backoffice); Visitante não autenticado (auto-cadastro via Portal Público)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir o cadastro e a edição de agências por dois fluxos distintos: (1) o Administrador cria ou edita uma agência manualmente no backoffice, acessando o formulário pelo botão "Adicionar Agência" na tela de Gestão de Agências (RF-044); (2) o Visitante não autenticado realiza o auto-cadastro pelo Portal Público (WF-004A), submetendo os dados da empresa, do responsável e os documentos necessários — após o envio, o cadastro fica com status "Pendente de Aprovação" até revisão e aprovação do Administrador. O formulário é organizado em três etapas: Dados da Empresa, Dados do Responsável e Dados Bancários.

**Requisitos Detalhados**

**Estrutura Geral e Navegação**

| ID        | Requisito |
|-----------|-----------|
| RF-045.01 | O sistema deve exibir o formulário de cadastro/edição dividido em três etapas sequenciais: Etapa 1 — Dados da Empresa, Etapa 2 — Dados do Responsável, Etapa 3 — Dados Bancários |
| RF-045.02 | O sistema deve exibir indicador de progresso (stepper) com os rótulos das três etapas, destacando a etapa atual |
| RF-045.03 | O sistema deve exibir botões "Anterior" e "Próximo" para navegação entre etapas, e botão "Salvar" na etapa final |
| RF-045.04 | O sistema deve validar os campos obrigatórios de cada etapa antes de permitir avançar para a próxima |
| RF-045.05 | O sistema deve exibir mensagens de erro inline abaixo de cada campo inválido, indicando o motivo da falha |
| RF-045.06 | No backoffice, o formulário deve ser exibido dentro de um modal ou página dedicada, acionado pelo botão "Adicionar Agência" (RF-044) |
| RF-045.07 | No Portal Público, o formulário deve ser exibido em página própria, acessível pelo CTA "Agente de Vendas" na home (WF-004A) |
| RF-045.08 | No modo de edição (Admin), o sistema deve pré-carregar todos os campos com os dados da agência selecionada |
| RF-045.09 | No modo de visualização (Admin), todos os campos devem estar desabilitados (somente leitura) |

**Etapa 1 — Dados da Empresa**

| ID        | Requisito |
|-----------|-----------|
| RF-045.10 | O sistema deve exibir campo "Nome Fantasia" (texto, obrigatório, máx. 150 caracteres) |
| RF-045.11 | O sistema deve exibir campo "Razão Social" (texto, obrigatório, máx. 200 caracteres) |
| RF-045.12 | O sistema deve exibir campo "CNPJ" (obrigatório, com máscara XX.XXX.XXX/XXXX-XX e validação de formato e dígitos verificadores) |
| RF-045.13 | O sistema deve exibir campo "Tipo de Empresa" (select obrigatório, com as opções: MEI, Microempresa, Empresa de Pequeno Porte, Empresa de Médio Porte, Empresa de Grande Porte) |
| RF-045.14 | O sistema deve exibir campo "CEP" com botão de busca automática que preenche Logradouro, Bairro, Cidade, UF e País via integração com serviço de CEP (obrigatório) |
| RF-045.15 | O sistema deve exibir campos de endereço: Logradouro (obrigatório), Número (obrigatório), Complemento (opcional), Bairro (obrigatório), Cidade (obrigatório), UF (select, obrigatório), País (obrigatório, padrão "Brasil") |
| RF-045.16 | O sistema deve exibir campo "Site/URL" (texto, opcional, com validação de formato de URL) |
| RF-045.17 | O sistema deve exibir campo "Telefone Comercial" (texto, obrigatório, com máscara para telefone fixo ou celular com DDD) |

**Etapa 2 — Dados do Responsável**

| ID        | Requisito |
|-----------|-----------|
| RF-045.18 | O sistema deve exibir campo "Nome Completo do Responsável" (texto, obrigatório, máx. 200 caracteres) |
| RF-045.19 | O sistema deve exibir campo "CPF do Responsável" (obrigatório, com máscara XXX.XXX.XXX-XX e validação de formato e dígitos verificadores) |
| RF-045.20 | O sistema deve exibir campo "E-mail de Acesso/Contato" (texto, obrigatório, com validação de formato de e-mail e verificação de unicidade no sistema) |
| RF-045.21 | O sistema deve exibir campo "Telefone Celular" (texto, obrigatório, com máscara para celular com DDD) |
| RF-045.22 | O sistema deve exibir campo "Idioma Padrão" (select, obrigatório, com as opções: Português, Inglês, Espanhol; padrão "Português") |
| RF-045.23 | No fluxo Admin (novo cadastro), o sistema deve exibir campo "Senha Inicial" (senha, obrigatório) e "Confirmar Senha" (senha, obrigatório) |
| RF-045.24 | No fluxo de auto-cadastro (Portal Público), o sistema deve exibir campo "Senha" (senha, obrigatório) escolhida pelo próprio usuário e "Confirmar Senha" (senha, obrigatório) |
| RF-045.25 | O sistema deve exibir indicador de força de senha (fraca, média, forte) em tempo real conforme o usuário digita |

**Etapa 3 — Dados Bancários**

| ID        | Requisito |
|-----------|-----------|
| RF-045.26 | O sistema deve exibir campo "Banco" (select com busca, obrigatório, listando os bancos brasileiros com código BACEN e nome) |
| RF-045.27 | O sistema deve exibir campo "Tipo de Conta" (radio ou select, obrigatório, com as opções: Corrente, Poupança) |
| RF-045.28 | O sistema deve exibir campo "Agência" (texto, obrigatório, com formato numérico e suporte a dígito verificador separado por hífen) |
| RF-045.29 | O sistema deve exibir campo "Conta Corrente" (texto, obrigatório, com dígito verificador separado por hífen) |
| RF-045.30 | O sistema deve exibir campo "Chave Pix" (texto, opcional, com select de tipo de chave: CPF, CNPJ, E-mail, Telefone, Chave Aleatória) |
| RF-045.31 | O sistema deve exibir campo "Titular da Conta" (texto, obrigatório, com indicação de que deve corresponder ao nome do contrato/CNPJ) |

**Upload de Documentos (Auto-cadastro — Portal Público)**

| ID        | Requisito |
|-----------|-----------|
| RF-045.32 | No fluxo de auto-cadastro, o sistema deve exibir seção de upload de documentos na Etapa 1 (Dados da Empresa) ou em etapa adicional |
| RF-045.33 | O sistema deve permitir upload de "Cartão CNPJ Atualizado" (PDF ou imagem, obrigatório no auto-cadastro, máx. 5 MB) |
| RF-045.34 | O sistema deve permitir upload de "Contrato Social ou Certificado MEI" (PDF, obrigatório no auto-cadastro, máx. 10 MB) |
| RF-045.35 | O sistema deve permitir upload de "RG ou CNH do Responsável" (imagem, obrigatório no auto-cadastro, máx. 5 MB) |
| RF-045.36 | No fluxo Admin (cadastro manual), os uploads de documentos são opcionais |
| RF-045.37 | O sistema deve exibir o nome do arquivo selecionado e botão para remover o documento antes do envio |
| RF-045.38 | O sistema deve exibir mensagem de erro ao tentar enviar arquivo com tipo ou tamanho fora dos limites permitidos |

**Comportamento Pós-envio**

| ID        | Requisito |
|-----------|-----------|
| RF-045.39 | Após envio pelo auto-cadastro, o sistema deve registrar a agência com status "Pendente de Aprovação" e enviar e-mail de confirmação de recebimento ao responsável |
| RF-045.40 | Após cadastro criado pelo Admin, o sistema deve registrar a agência com status imediato "Ativa" e enviar e-mail de boas-vindas ao responsável com a senha provisória |
| RF-045.41 | Após edição pelo Admin, o sistema deve salvar as alterações e enviar e-mail de atualização de cadastro ao responsável da agência |
| RF-045.42 | O sistema deve exibir mensagem de sucesso na tela ao concluir o cadastro ou edição |

**Regras de Negócio**

| ID        | Regra |
|-----------|-------|
| RN-045.01 | O CNPJ deve ser único no sistema; o sistema deve rejeitar cadastros com CNPJ já existente e exibir mensagem de erro específica |
| RN-045.02 | O e-mail do responsável deve ser único no sistema e torna-se o login da Agência no backoffice após aprovação |
| RN-045.03 | Agências cadastradas via auto-cadastro recebem automaticamente o status "Pendente de Aprovação" e só podem acessar o backoffice após aprovação pelo Administrador (via RF-044) |
| RN-045.04 | Agências cadastradas manualmente pelo Administrador recebem status imediato "Ativa", sem necessidade de aprovação |
| RN-045.05 | A senha provisória definida pelo Admin no cadastro deve ser redefinida pelo usuário no primeiro acesso ao backoffice |
| RN-045.06 | A senha deve ter no mínimo 8 caracteres, contendo pelo menos uma letra maiúscula, uma letra minúscula, um número e um caractere especial |
| RN-045.07 | O preenchimento automático de endereço via CEP não deve impedir a edição manual dos campos pelo usuário |
| RN-045.08 | Os documentos enviados no auto-cadastro ficam armazenados de forma segura e são visíveis apenas para o Administrador no backoffice |
| RN-045.09 | O Administrador pode alterar o status da agência manualmente ao editar o cadastro (ex.: de "Pendente de Aprovação" para "Ativa" ou "Inativa") |
| RN-045.10 | O campo "Titular da Conta" deve corresponder ao nome jurídico vinculado ao CNPJ da agência para fins de validação financeira |
| RN-045.11 | A validação de CNPJ e CPF deve verificar o formato e os dígitos verificadores; CNPJs ou CPFs matematicamente inválidos devem ser rejeitados com mensagem de erro |
| RN-045.12 | Arquivos de documentos enviados devem ser armazenados com controle de versão; ao reeditar e renviar um documento, a versão anterior deve ser mantida no histórico |

**Critérios de Aceitação**

**Fluxo Admin — Novo Cadastro**

| ID        | Critério | Resultado Esperado |
|-----------|----------|--------------------|
| CA-045.01 | Admin clica em "Adicionar Agência" na RF-044 | Formulário de cadastro em branco é exibido na Etapa 1 |
| CA-045.02 | Admin preenche Etapa 1 e clica "Próximo" sem preencher campo obrigatório (ex.: CNPJ) | Mensagem de erro exibida abaixo do campo; navegação bloqueada |
| CA-045.03 | Admin informa CNPJ já cadastrado no sistema | Mensagem "CNPJ já cadastrado" exibida; navegação bloqueada |
| CA-045.04 | Admin preenche todas as etapas e clica "Salvar" | Agência criada com status "Ativa"; e-mail de boas-vindas enviado ao responsável com senha provisória |
| CA-045.05 | Admin informa e-mail já existente no sistema | Mensagem "E-mail já cadastrado" exibida; navegação bloqueada |

**Fluxo Admin — Edição**

| ID        | Critério | Resultado Esperado |
|-----------|----------|--------------------|
| CA-045.06 | Admin seleciona agência existente e aciona "Editar" na RF-044 | Formulário abre em modo edição com dados pré-carregados |
| CA-045.07 | Admin altera o status da agência de "Pendente de Aprovação" para "Ativa" e salva | Status atualizado; e-mail de atualização enviado ao responsável |
| CA-045.08 | Admin edita o campo "Nome Fantasia" e salva | Alteração persistida; mensagem de sucesso exibida |

**Fluxo Auto-cadastro — Portal Público**

| ID        | Critério | Resultado Esperado |
|-----------|----------|--------------------|
| CA-045.09 | Visitante acessa WF-004A pelo CTA "Agente de Vendas" na home do Portal | Formulário de auto-cadastro exibido com stepper de 3 etapas |
| CA-045.10 | Visitante conclui todas as etapas e envia o formulário sem documentos obrigatórios | Mensagem de erro indicando os documentos ausentes; envio bloqueado |
| CA-045.11 | Visitante tenta fazer upload de arquivo acima do limite (ex.: PDF de 12 MB para Contrato Social) | Mensagem "Arquivo excede o tamanho máximo permitido (10 MB)" exibida; arquivo rejeitado |
| CA-045.12 | Visitante conclui todas as etapas corretamente e envia o formulário | Agência registrada com status "Pendente de Aprovação"; e-mail de confirmação enviado ao responsável |
| CA-045.13 | Agência com status "Pendente de Aprovação" tenta acessar o backoffice | Acesso negado com mensagem informando que o cadastro está em análise |

**Validações de Campos**

| ID        | Critério | Resultado Esperado |
|-----------|----------|--------------------|
| CA-045.14 | Usuário informa CNPJ com dígitos verificadores incorretos (ex.: 11.222.333/0001-00) | Mensagem "CNPJ inválido" exibida; campo marcado com erro |
| CA-045.15 | Usuário informa CPF com dígitos verificadores incorretos | Mensagem "CPF inválido" exibida; campo marcado com erro |
| CA-045.16 | Usuário preenche "Confirmar Senha" diferente do campo "Senha" | Mensagem "As senhas não coincidem" exibida; botão de avançar/salvar bloqueado |
| CA-045.17 | Usuário informa CEP válido e clica no botão de busca | Campos Logradouro, Bairro, Cidade, UF e País são preenchidos automaticamente |
| CA-045.18 | Usuário informa URL inválida no campo "Site/URL" | Mensagem "URL inválida" exibida; campo marcado com erro |

**Protótipo/Wireframe**

Figura - WF-049 - Cadastro de Agência.png (a definir)

Figura - WF-004A - Cadastro de Agência (Portal).png
