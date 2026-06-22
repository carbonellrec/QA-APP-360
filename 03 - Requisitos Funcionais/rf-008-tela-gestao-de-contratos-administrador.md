### 3.8 Tela Gestão de Contratos - Administrador

**ID:** RF-008

Módulo: Gestão de Contratos

Perfis com Acesso: Administrador (CRUD), Parceiro Comercial (Visualização)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador visualize, gerencie e acompanhe os contratos das atrações. Os contratos são agrupados por Parceiro Comercial, permitindo expandir para visualizar os contratos individuais de cada atração. O módulo integra com Docusign para coleta de assinaturas digitais.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-008.01 | O sistema deve exibir título "Gestão de Contratos" com subtítulo "Gerencie os contratos do sistema" |
| RF-008.02 | O sistema deve exibir campo de busca para pesquisa                                                  |
| RF-008.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                         |
| RF-008.04 | O sistema deve exibir botão "Adicionar Contrato"                                                    |
| RF-008.05 | O sistema deve exibir abas para filtrar contratos:  **Ativos**  ,  **Inativos**  ,  **Todos**       |

Tipos de Contrato

| Tipo de Contrato    | Usuário Vinculado   | Descrição                                                   |
|---------------------|---------------------|-------------------------------------------------------------|
| Contrato de Atração | Parceiro Comercial  | Contrato para exploração comercial de uma atração turística |
| Contrato de Agência | Agência             | Contrato para divulgação da plataforma e atrações           |

Tabela Principal (Parceiros Comerciais)

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-008.06 | O sistema deve exibir lista de  **Parceiros Comerciais e Agências**  que possuem contratos |
| RF-008.07 | O sistema deve exibir ícone de expansão (seta) em cada linha de Parceiro                   |
| RF-008.08 | Ao clicar na linha ou seta, o sistema deve expandir e exibir os contratos do Parceiro      |

Colunas da Tabela Principal:

| Coluna                  | Descrição                           | Ordenável   |
|-------------------------|-------------------------------------|-------------|
| Ícone de expansão       | Seta para expandir/recolher         | ❌           |
| ID Parceiro/Agência     | ID do Parceiro Comercial ou Agência | ✅           |
| Nome Parceiro Comercial | Nome do Parceiro (com foto/avatar)  | ✅           |
| Tipo                    | Parceiro Comercial / Agência        |             |

Tabela Expandida (Contratos)

| ID        | Requisito                                                                       |
|-----------|---------------------------------------------------------------------------------|
| RF-008.09 | O sistema deve exibir tabela com os contratos do Parceiro Comercial selecionado |
| RF-008.10 | O sistema deve exibir checkbox em cada linha para seleção múltipla              |
| RF-008.11 | Cada contrato está vinculado a uma atração específica                           |

Colunas da Tabela de Contratos:

| Coluna         | Descrição                                 | Ordenável   |
|----------------|-------------------------------------------|-------------|
| Checkbox       | Seleção do contrato                       | ❌           |
| Contrato ID    | Identificador único do contrato           | ✅           |
| Nome Atração   | Nome da atração vinculada ao contrato     | ✅           |
| Status         | Status atual do contrato (badge colorido) | ✅           |
| Data Expiração | Data de expiração do contrato             | ✅           |

Status do Contrato

| Status             | Descrição                                          | Cor Sugerida   | Transição            |
|--------------------|----------------------------------------------------|----------------|----------------------|
| Rascunho           | Contrato em preenchimento                          | 🔘 Cinza        | → Aguardando Envio   |
| Aguardando Envio   | Contrato totalmente preenchido, pronto para enviar | 🟡 Amarelo      | → Enviado a Docusign |
| Enviado a Docusign | Aguardando assinaturas na plataforma Docusign      | 🔵 Azul         | → Ativo              |
| Ativo              | Contrato assinado e vigente                        | 🟢 Verde        | → Expirado / Inativo |
| Expirado           | Data de expiração atingida (automático)            | 🟠 Laranja      | -                    |
| Inativo            | Cancelado ou desativado manualmente                | ⚫ Cinza escuro | -                    |

Barra de Ações (ao selecionar contratos)

| ID        | Requisito                                                                                      |
|-----------|------------------------------------------------------------------------------------------------|
| RF-008.12 | O sistema deve exibir contador "Selecionados X" indicando quantidade de contratos selecionados |
| RF-008.13 | O sistema deve exibir barra de ações quando houver pelo menos 1 contrato selecionado           |

Ações Disponíveis:

| Ação                  | Seleção    | Descrição                                  |
|-----------------------|------------|--------------------------------------------|
| Enviar Docusign       | Múltiplos* | Envia contratos para coleta de assinaturas |
| Download PDF          | Múltiplos  | Baixa o PDF do contrato preenchido         |
| Editar                | Apenas 1   | Abre tela de edição (RF-009)               |
| Excluir               | Múltiplos  | Exclui contratos (soft delete)             |
| Inativar selecionados | Múltiplos  | Muda status para "Inativo"                 |

*Nota: Envio em massa para Docusign sujeito a limitações da integração (a confirmar com equipe técnica)*

Funcionalidades de Busca e Filtro

Campo de Busca

| ID        | Requisito                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| RF-008.14 | O sistema deve permitir busca por texto livre                                                        |
| RF-008.15 | A busca deve pesquisar nos campos: ID do Parceiro, Nome do Parceiro, ID do Contrato, Nome da Atração |
| RF-008.16 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                            |

Filtros Avançados

| Filtro             | Tipo             | Opções                                                                   |
|--------------------|------------------|--------------------------------------------------------------------------|
| Status             | Multi-select     | Rascunho, Aguardando Envio, Enviado a Docusign, Ativo, Expirado, Inativo |
| Data de Expiração  | Range de datas   | De / Até                                                                 |
| Parceiro Comercial | Select com busca | Lista de Parceiros                                                       |
| Atração            | Select com busca | Lista de Atrações                                                        |
| Tipo de Contrato   | Select           | Parceiro Comercial, Agência, Todos                                       |

Paginação

| ID        | Requisito                                                                                 |
|-----------|-------------------------------------------------------------------------------------------|
| RF-008.17 | O sistema deve carregar por padrão  **10 Parceiros Comerciais**  por página               |
| RF-008.18 | O sistema deve permitir alterar para exibir 10, 20, 50 ou 100 registros                   |
| RF-008.19 | O sistema deve exibir navegação: primeira página, anterior, "X a Y de Z", próxima, última |

Regras de Negócio

| ID        | Regra                                                                                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RN-008.01 | Os contratos são  **agrupados por Parceiro Comercial**  na visualização principal                                         |
| RN-008.02 | Cada  **contrato está vinculado a uma única atração**                                                                     |
| RN-008.03 | Um Parceiro Comercial pode ter  **múltiplas atrações**  , cada uma com seu próprio contrato                               |
| RN-008.04 | As abas filtram contratos por status:  **Ativos**  (status Ativo),  **Inativos**  (status Inativo + Expirado),  **Todos** |
| RN-008.05 | Contratos em preenchimento recebem status  **"Rascunho"**                                                                 |
| RN-008.06 | Contratos totalmente preenchidos recebem status  **"Aguardando Envio"**                                                   |
| RN-008.07 | Contratos enviados para Docusign recebem status  **"Enviado a Docusign"**                                                 |
| RN-008.08 | Após confirmação de todas as assinaturas, status muda automaticamente para  **"Ativo"**                                   |
| RN-008.09 | Quando a  **data de expiração**  é atingida, o sistema muda automaticamente o status para  **"Expirado"**                 |
| RN-008.10 | O status  **"Inativo"**  é aplicado por cancelamento ou ação manual do administrador                                      |
| RN-008.11 | A ação  **"Excluir"**  realiza soft delete (marca como excluído no banco, não remove fisicamente)                         |
| RN-008.12 | O botão  **"Editar"**  só é habilitado quando  **apenas 1 contrato**  está selecionado                                    |
| RN-008.13 | O  **Download PDF**  baixa o arquivo do contrato já preenchido com os dados (Razão Social, CNPJ, etc.)                    |
| RN-008.14 | Ao clicar em  **"Enviar Docusign"**  , o sistema abre preview do contrato para revisão antes do envio                     |
| RN-008.15 | Ao clicar em  **"Excluir"**  , o sistema exibe confirmação: "Deseja realmente excluir o(s) contrato(s) selecionado(s)?"   |
| RN-008.16 | A integração com Docusign utiliza a  **conta da plataforma Curitiba 360**                                                 |
| RN-008.17 | Os  **signatários**  do contrato são: Curitiba 360 (plataforma) e o Parceiro Comercial                                    |
| RN-008.18 | Somente contratos com status  **"Aguardando Envio"**  podem ser enviados para Docusign                                    |
| RN-008.19 | Contratos excluídos (soft delete)  **não aparecem**  em nenhuma aba                                                       |
| RN-008.20 | Existem dois tipos de contrato: Contrato de Atração (Parceiro Comercial) e Contrato de Agência                            |
| RN-008.21 | Contratos de Parceiro Comercial são vinculados a uma atração específica                                                   |
| RN-008.22 | Contratos de Agência são vinculados diretamente à agência (sem atração)                                                   |
| RN-008.23 | O Contrato de Agência pode ser gerado de duas formas: (1) **automaticamente**, quando o Administrador aprova uma agência em RF-044 — o sistema cria o contrato pré-preenchido com os dados de RF-045 com status "Aguardando Envio"; (2) **manualmente**, pelo Administrador via botão "Adicionar Contrato" nesta tela. |
| RN-008.24 | Enquanto o Contrato de Agência não atingir o status "Ativo" (assinaturas coletadas via DocuSign), a agência permanece bloqueada para operações comerciais — seus agentes não podem realizar vendas na plataforma (RF-044 RN-044.15). |
| RN-008.25 | O fluxo completo de ativação de uma agência é: Cadastro (RF-045) → Aprovação pelo Admin (RF-044) → Geração automática do contrato pré-preenchido (RF-008, status "Aguardando Envio") → Admin revisa e envia ao DocuSign → Coleta de assinaturas → Contrato "Ativo" → Agência liberada para operar. |
| RN-008.26 | O Contrato de Atração (Parceiro Comercial) pode ser gerado de duas formas: (1) **automaticamente**, quando o Admin aprova um Parceiro Comercial em RF-057 — o sistema cria o contrato com status "Rascunho" pré-preenchido com os dados cadastrais do parceiro (RF-053); o Admin deve complementar com os dados da atração antes de enviar ao DocuSign; (2) **manualmente**, pelo Admin via botão "Adicionar Contrato" nesta tela, quando o Parceiro é criado diretamente via RF-007. |
| RN-008.27 | Enquanto o Contrato de Atração de um Parceiro Comercial não atingir o status "Ativo" (assinaturas coletadas via DocuSign), a atração vinculada permanece bloqueada para operações comerciais — não permite venda de ingressos na plataforma. |
| RN-008.28 | O fluxo completo de ativação de um Parceiro Comercial (auto-cadastro) é: Cadastro no Portal (RF-053) → Notificação ao Admin → Aprovação pelo Admin (RF-057) → Credenciais do Backoffice enviadas + Contrato de Atração "Rascunho" gerado (RF-008) → Admin complementa contrato com dados da atração e envia ao DocuSign → Coleta de assinaturas → Contrato "Ativo" → Atração liberada para operação comercial. |

Critérios de Aceitação

Visualização e Navegação

| ID        | Critério                                 | Resultado Esperado                                       |
|-----------|------------------------------------------|----------------------------------------------------------|
| CA-008.01 | Acessar Gestão de Contratos              | Lista de Parceiros Comerciais com contratos é exibida    |
| CA-008.02 | Clicar na linha de um Parceiro Comercial | Contratos do parceiro são expandidos/exibidos            |
| CA-008.03 | Clicar na seta de expansão               | Contratos são expandidos/recolhidos                      |
| CA-008.04 | Selecionar aba "Ativos"                  | Apenas contratos com status "Ativo" são exibidos         |
| CA-008.05 | Selecionar aba "Inativos"                | Contratos com status "Inativo" e "Expirado" são exibidos |
| CA-008.06 | Selecionar aba "Todos"                   | Todos os contratos são exibidos (exceto excluídos)       |

Busca e Filtros

| ID        | Critério                       | Resultado Esperado                                           |
|-----------|--------------------------------|--------------------------------------------------------------|
| CA-008.07 | Pesquisar por nome do Parceiro | Parceiros que correspondem à busca são exibidos              |
| CA-008.08 | Pesquisar por ID do contrato   | Parceiro com o contrato correspondente é exibido (expandido) |
| CA-008.09 | Filtrar por status             | Apenas contratos com o status selecionado são exibidos       |
| CA-008.10 | Filtrar por data de expiração  | Contratos dentro do período são exibidos                     |

Seleção e Ações

| ID        | Critério                                          | Resultado Esperado                         |
|-----------|---------------------------------------------------|--------------------------------------------|
| CA-008.11 | Selecionar checkbox de um contrato                | Barra de ações aparece com todas as opções |
| CA-008.12 | Selecionar múltiplos contratos                    | Contador "Selecionados X" é atualizado     |
| CA-008.13 | Selecionar 2+ contratos                           | Botão "Editar" fica  **desabilitado**      |
| CA-008.14 | Selecionar apenas 1 contrato e clicar em "Editar" | Sistema abre tela de edição (RF-009)       |

Ações de Contrato

| ID        | Critério                          | Resultado Esperado                                 |
|-----------|-----------------------------------|----------------------------------------------------|
| CA-008.15 | Clicar em "Download PDF"          | Sistema baixa o arquivo PDF do contrato preenchido |
| CA-008.16 | Clicar em "Excluir"               | Modal de confirmação é exibido                     |
| CA-008.17 | Confirmar exclusão                | Contrato é removido da lista (soft delete)         |
| CA-008.18 | Clicar em "Inativar selecionados" | Status dos contratos muda para "Inativo"           |

Integração Docusign

| ID        | Critério                                                             | Resultado Esperado                                                                 |
|-----------|----------------------------------------------------------------------|------------------------------------------------------------------------------------|
| CA-008.19 | Selecionar contrato "Aguardando Envio" e clicar em "Enviar Docusign" | Modal de preview é exibido                                                         |
| CA-008.20 | Confirmar envio no preview                                           | Contrato é enviado para Docusign + status muda para "Enviado a Docusign"           |
| CA-008.21 | Selecionar contrato "Rascunho" e clicar em "Enviar Docusign"         | Mensagem de erro: "Contrato incompleto. Finalize o preenchimento antes de enviar." |
| CA-008.22 | Docusign confirma assinaturas (via webhook)                          | Status do contrato muda automaticamente para "Ativo"                               |

Automações

| ID        | Critério                                            | Resultado Esperado                                  |
|-----------|-----------------------------------------------------|-----------------------------------------------------|
| CA-008.23 | Data de expiração de um contrato "Ativo" é atingida | Sistema muda status automaticamente para "Expirado" |
| CA-008.24 | Verificar contrato expirado na aba "Inativos"       | Contrato expirado aparece na lista                  |

Paginação

| ID        | Critério                             | Resultado Esperado                           |
|-----------|--------------------------------------|----------------------------------------------|
| CA-008.25 | Alterar quantidade para 50 registros | Sistema exibe até 50 Parceiros por página    |
| CA-008.26 | Clicar em "Próxima página"           | Sistema carrega próxima página de resultados |

Protótipo/Wireframe

Figura  - WF-007 - Gestão de Contratos.png

### 3.9 Incluir Contratos - Administrador
