### 10.2 CU-031 - Cadastro de Agência

ID: CU-031

Nome: Cadastro de Agência

Ator Principal: Administrador (cadastro/edição manual no Backoffice); Visitante não autenticado (auto-cadastro via Portal Público)

Atores Secundários: Sistema (validação de CNPJ/CPF, integração com serviço de CEP, envio de e-mails, armazenamento de documentos, módulo de Contratos RF-008)

Pré-condições: No fluxo Admin, usuário autenticado com perfil Administrador acessa "Adicionar Agência" em RF-044; no auto-cadastro, visitante acessa o CTA "Agente de Vendas" no Portal Público (WF-004A)

Pós-condições: Agência registrada no sistema com status "Aguardando Contrato" (cadastro Admin) ou "Pendente de Aprovação" (auto-cadastro); e-mail de confirmação ou de boas-vindas enviado ao responsável; documentos (auto-cadastro) armazenados de forma segura; rascunho de Contrato de Agência gerado no módulo RF-008 — acesso ao backoffice e liberação de vendas concedidos automaticamente pelo sistema apenas quando o contrato atingir status "Ativo" via DocuSign (RN-045.13).

Requisitos Relacionados: RF-045

Fluxo Principal:

1. O ator acessa o formulário de cadastro de agência (modal/página no Backoffice ou página pública WF-004A).
2. O sistema exibe a Etapa 1 — Dados da Empresa, com indicador de progresso (stepper de 3 etapas).
3. O ator preenche Nome Fantasia, Razão Social, CNPJ (formato numérico ou alfanumérico, conforme vigência), Tipo de Empresa, CEP (com busca automática), endereço completo, Site/URL e Telefone Comercial; no auto-cadastro, anexa também os documentos obrigatórios.
4. O sistema valida os campos obrigatórios e formatos (CNPJ — numérico ou alfanumérico conforme data vigente —, URL, máscara de telefone) e libera a navegação para a Etapa 2.
5. O ator preenche Etapa 2 — Dados do Responsável (Nome, CPF, E-mail, Telefone Celular, Idioma Padrão e Senha) e o sistema valida unicidade de e-mail e regras de senha.
6. O ator preenche Etapa 3 — Dados Bancários (Banco, Tipo de Conta, Agência, Conta, Chave Pix opcional, Titular) e clica em "Salvar".
7. O sistema persiste o cadastro: no fluxo Admin atribui status "Aguardando contrato"  e gera automaticamente o rascunho de Contrato de Agência no módulo RF-008; e envia e-mail informando que o contrato foi gerado e aguarda assinatura; no auto-cadastro atribui status "Pendente de Aprovação" e envia e-mail de confirmação de recebimento. 
7B. Falha na geração do rascunho do Contrato de Agência (RF-008) após cadastro pelo Admin: sistema mantém o cadastro com status "Aguardando Contrato", exibe alerta ao Administrador e oferece nova tentativa manual de geração do contrato.

8. O sistema exibe mensagem de sucesso — no fluxo Admin, informando também que o contrato foi gerado e aguarda assinatura para acesso ao backoffice e liberação de vendas — e, no Backoffice, retorna à listagem RF-044.
9. Ao receber a confirmação de contrato com status "Ativo" no módulo RF-008 (todas as assinaturas via DocuSign coletadas), o sistema altera automaticamente o status da agência de "Aguardando Contrato" para "Ativa", libera o acesso ao backoffice e envia e-mail de boas-vindas ao responsável com as credenciais de acesso.

Fluxos de Exceção:

4a. Campo obrigatório não preenchido: Sistema exibe mensagem de erro inline e bloqueia a navegação.
4b. CNPJ com dígitos verificadores inválidos (numérico ou alfanumérico, conforme formato vigente na data): Sistema exibe "CNPJ inválido" e bloqueia o avanço.
4c. CNPJ já cadastrado no sistema: Sistema exibe "CNPJ já cadastrado" e bloqueia a navegação.
5a. E-mail do responsável já cadastrado: Sistema exibe "E-mail já cadastrado" e bloqueia o avanço.
5b. Senha não atende às regras de complexidade ou "Confirmar Senha" diferente: Sistema exibe mensagem específica e bloqueia o avanço.
6a. Upload de documento (auto-cadastro) com tipo ou tamanho fora do permitido: Sistema rejeita o arquivo e exibe mensagem de erro.
7a. Falha no envio de e-mail: Sistema mantém o cadastro, registra o erro no log e notifica o Administrador.
7b. Falha na geração do rascunho de Contrato de Agência (RF-008) após cadastro pelo Admin: Sistema mantém o cadastro com status "Ativa", exibe alerta ao Administrador e oferece nova tentativa manual de geração do contrato.
9a.Se a confirmação do RF-008 falhar ao tentar ativar a agência o sistema mantém o status "Aguardando Contrato", registra o erro no log e notifica o Administrador para verificar o contrato no RF-008.
9b. Se o e-mail de boas-vindas falhar o sistema mantém o status "Ativa" e o acesso ao backoffice liberado, registra o erro no log e notifica o Administrador.
9c. A senha provisória já expirou ou foi invalidada antes do contrato ser assinado o sistema envia o e-mail de boas-vindas com link de redefinição de senha em vez da senha provisória, orientando o responsável a cadastrar uma nova senha no primeiro acesso.