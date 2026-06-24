### 10.2 CU-031 - Cadastro de Agência

ID: CU-031

Nome: Cadastro de Agência

Ator Principal: Administrador (cadastro/edição manual no Backoffice); Visitante não autenticado (auto-cadastro via Portal Público)

Atores Secundários: Sistema (validação de CNPJ/CPF, integração com serviço de CEP, envio de e-mails, armazenamento de documentos, módulo de Contratos RF-008)

Pré-condições: No fluxo Admin, usuário autenticado com perfil Administrador acessa "Adicionar Agência" em RF-044; no auto-cadastro, visitante acessa o CTA "Agente de Vendas" no Portal Público (WF-004A)

Pós-condições: Agência registrada no sistema com status "Ativa" (cadastro Admin) ou "Pendente de Aprovação" (auto-cadastro); e-mail de confirmação ou de boas-vindas enviado ao responsável; documentos (auto-cadastro) armazenados de forma segura; no fluxo Admin, rascunho de Contrato de Agência gerado no módulo RF-008 com Substatus "Bloqueada para Vendas", liberado apenas quando o contrato atingir status "Ativo" via DocuSign

Requisitos Relacionados: RF-045

Fluxo Principal:

1. O ator acessa o formulário de cadastro de agência (modal/página no Backoffice ou página pública WF-004A).
2. O sistema exibe a Etapa 1 — Dados da Empresa, com indicador de progresso (stepper de 3 etapas).
3. O ator preenche Nome Fantasia, Razão Social, CNPJ (formato numérico ou alfanumérico, conforme vigência), Tipo de Empresa, CEP (com busca automática), endereço completo, Site/URL e Telefone Comercial; no auto-cadastro, anexa também os documentos obrigatórios.
4. O sistema valida os campos obrigatórios e formatos (CNPJ — numérico ou alfanumérico conforme data vigente —, URL, máscara de telefone) e libera a navegação para a Etapa 2.
5. O ator preenche Etapa 2 — Dados do Responsável (Nome, CPF, E-mail, Telefone Celular, Idioma Padrão e Senha) e o sistema valida unicidade de e-mail e regras de senha.
6. O ator preenche Etapa 3 — Dados Bancários (Banco, Tipo de Conta, Agência, Conta, Chave Pix opcional, Titular) e clica em "Salvar".
7. O sistema persiste o cadastro: no fluxo Admin atribui status "Aguardando contrato" (acesso ao backoffice), dispara e-mail de boas-vindas com senha provisória e gera automaticamente o rascunho de Contrato de Agência no módulo RF-008 com Substatus "Bloqueada para Vendas"; e envia e-mail de confirmação de recebimento.
8. O sistema exibe mensagem de sucesso — no fluxo Admin, informando também que o contrato foi gerado e aguarda assinatura para liberação de vendas — e, no Backoffice, retorna à listagem RF-044.

Fluxos de Exceção:

4a. Campo obrigatório não preenchido: Sistema exibe mensagem de erro inline e bloqueia a navegação.
4b. CNPJ com dígitos verificadores inválidos (numérico ou alfanumérico, conforme formato vigente na data): Sistema exibe "CNPJ inválido" e bloqueia o avanço.
4c. CNPJ já cadastrado no sistema: Sistema exibe "CNPJ já cadastrado" e bloqueia a navegação.
5a. E-mail do responsável já cadastrado: Sistema exibe "E-mail já cadastrado" e bloqueia o avanço.
5b. Senha não atende às regras de complexidade ou "Confirmar Senha" diferente: Sistema exibe mensagem específica e bloqueia o avanço.
6a. Upload de documento (auto-cadastro) com tipo ou tamanho fora do permitido: Sistema rejeita o arquivo e exibe mensagem de erro.
7a. Falha no envio de e-mail: Sistema mantém o cadastro, registra o erro no log e notifica o Administrador.
7b. Falha na geração do rascunho de Contrato de Agência (RF-008) após cadastro pelo Admin: Sistema mantém o cadastro com status "Ativa" e Substatus "Bloqueada para Vendas", exibe alerta ao Administrador e oferece nova tentativa manual de geração do contrato.
