### 3.57 Gestão de Parceiros Comerciais - Administrador

**ID:** RF-057

Módulo: Gestão de Parceiros Comerciais

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Tela de listagem e gerenciamento de todos os Parceiros Comerciais cadastrados no sistema. O Administrador pode buscar, filtrar, visualizar, aprovar, rejeitar, suspender, reativar, inativar e excluir parceiros, além de cadastrar novos por meio do botão "Adicionar Parceiro". A aprovação concede acesso ao Backoffice e gera automaticamente um Contrato de Atração em rascunho no módulo de Gestão de Contratos (RF-008), a ser complementado pelo Admin com os dados da atração antes do envio ao DocuSign.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.01 | O sistema deve exibir o título "Gestão de Parceiros Comerciais" com subtítulo "Gerencie os parceiros comerciais cadastrados no sistema" |
| RF-057.02 | O sistema deve exibir campo de busca por texto (busca por Razão Social, Nome Fantasia, CNPJ e e-mail do responsável)                   |
| RF-057.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                                                            |
| RF-057.04 | O sistema deve exibir botão "Adicionar Parceiro" para cadastrar novo parceiro comercial                                                |
| RF-057.05 | O sistema deve exibir abas para filtrar por status: "Ativas", "Pendente de Aprovação", "Suspensas", "Inativas", "Todas"               |
| RF-057.06 | O sistema deve exibir a aba "Ativas" selecionada por padrão                                                                            |

Tabela de Parceiros Comerciais

| ID        | Requisito                                                                                                                                                          |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.07 | O sistema deve exibir tabela com os parceiros comerciais cadastrados conforme a aba selecionada                                                                    |
| RF-057.08 | A tabela deve exibir as colunas: Checkbox, ID, Razão Social (com logo/avatar), Nome Fantasia, CNPJ, E-mail Responsável, Status, Qtd Atrações, Data de Cadastro   |
| RF-057.09 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                                                                              |
| RF-057.10 | A ordenação padrão deve ser por ID decrescente (mais recente primeiro)                                                                                             |
| RF-057.11 | A coluna Status deve exibir badge visual com cor diferenciada: Ativa (verde), Pendente (amarelo), Suspensa (laranja), Inativa (cinza)                             |
| RF-057.12 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização somente leitura com resumo do parceiro                              |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.13 | O sistema deve exibir checkbox na primeira coluna para seleção de parceiros                                                           |
| RF-057.14 | O sistema deve permitir selecionar múltiplos parceiros via checkbox                                                                   |
| RF-057.15 | Ao selecionar um ou mais parceiros, o sistema deve exibir barra de ações com contador "Selecionados X"                                |
| RF-057.16 | Na aba "Pendente de Aprovação", a barra de ações deve exibir: "Aprovar selecionados", "Rejeitar selecionados", "Solicitar Documentação Pendente" |
| RF-057.17 | Na aba "Ativas", a barra de ações deve exibir: "Editar", "Suspender selecionados", "Inativar selecionados", "Excluir"                 |
| RF-057.18 | Na aba "Suspensas", a barra de ações deve exibir: "Editar", "Reativar selecionados", "Inativar selecionados", "Excluir"               |
| RF-057.19 | Na aba "Inativas", a barra de ações deve exibir: "Editar", "Reativar selecionados", "Excluir"                                         |
| RF-057.20 | O botão "Editar" deve estar habilitado apenas quando **exatamente 1 parceiro** estiver selecionado                                   |
| RF-057.21 | Os botões de ação em massa devem funcionar para múltiplos parceiros selecionados                                                      |

Paginação

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-057.22 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100   |
| RF-057.23 | O sistema deve exibir indicador de registros: "X a Y de Z"                                       |
| RF-057.24 | O sistema deve exibir navegação: primeira página, anterior, página atual, próxima, última página  |

Ações Detalhadas - Aprovar

| ID        | Requisito                                                                                                                                                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.25 | Ao clicar em "Aprovar selecionados", o sistema deve exibir modal de confirmação com a quantidade de parceiros                                                                                                                          |
| RF-057.26 | Ao confirmar, o sistema deve alterar o status dos parceiros para "Ativa"                                                                                                                                                              |
| RF-057.27 | O sistema deve enviar e-mail ao responsável de cada parceiro aprovado contendo: boas-vindas, credenciais de acesso ao Backoffice (usuário e senha temporária) e instruções de primeiro acesso                                         |
| RF-057.28 | O sistema deve gerar automaticamente um **Contrato de Atração** com status "Rascunho" no módulo RF-008 para cada parceiro aprovado, pré-preenchido com os dados cadastrais do parceiro (Razão Social, CNPJ, responsável)             |
| RF-057.29 | O sistema deve exibir mensagem de sucesso informando quantos parceiros foram aprovados                                                                                                                                                 |

Ações Detalhadas - Rejeitar

| ID        | Requisito                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.30 | Ao clicar em "Rejeitar selecionados", o sistema deve exibir modal com campo de motivo obrigatório                                   |
| RF-057.31 | O sistema deve impedir a confirmação da rejeição se o campo de motivo estiver vazio, exibindo mensagem de erro                      |
| RF-057.32 | Ao confirmar, o sistema deve alterar o status dos parceiros para "Inativa"                                                           |
| RF-057.33 | O sistema deve enviar e-mail ao responsável de cada parceiro rejeitado informando o motivo da rejeição e instruções para recurso    |
| RF-057.34 | O sistema deve exibir mensagem de sucesso informando quantos parceiros foram rejeitados                                              |

Ações Detalhadas - Solicitar Documentação Pendente (Novo)

| ID        | Requisito                                                                                                                                                          |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.50 | Ao clicar em "Solicitar Documentação Pendente" (disponível apenas com 1 parceiro selecionado, na aba "Pendente de Aprovação"), o sistema deve exibir modal com campo de texto obrigatório para descrever a documentação ou informação faltante |
| RF-057.51 | O sistema deve impedir a confirmação se o campo de descrição da pendência estiver vazio, exibindo mensagem de erro                                                |
| RF-057.52 | Ao confirmar, o sistema deve manter o status do parceiro como "Pendente de Aprovação" (sem alteração de status) e enviar e-mail ao responsável informando a pendência descrita, já que o parceiro ainda não possui acesso ao Backoffice                |
| RF-057.53 | O sistema deve registrar a solicitação de documentação no histórico do parceiro, com data, descrição da pendência e Administrador responsável                    |
| RF-057.54 | O sistema deve exibir mensagem de sucesso confirmando o envio da solicitação de documentação                                                                     |

Ações Detalhadas - Suspender

| ID        | Requisito                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.35 | Ao clicar em "Suspender selecionados", o sistema deve exibir modal de confirmação com campo de motivo opcional                      |
| RF-057.36 | Ao confirmar, o sistema deve alterar o status dos parceiros para "Suspensa"                                                          |
| RF-057.37 | Todos os Editores e Leitores vinculados aos parceiros suspensos devem ter seus acessos bloqueados (não podem acessar o Backoffice)  |
| RF-057.38 | O sistema deve exibir mensagem de sucesso informando quantos parceiros foram suspensos                                               |

Ações Detalhadas - Reativar

| ID        | Requisito                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.39 | Ao clicar em "Reativar selecionados", o sistema deve exibir modal de confirmação com a quantidade de parceiros                      |
| RF-057.40 | Ao confirmar, o sistema deve alterar o status dos parceiros para "Ativa"                                                             |
| RF-057.41 | Todos os Editores e Leitores vinculados aos parceiros reativados devem ter seus acessos restabelecidos                              |
| RF-057.42 | O sistema deve exibir mensagem de sucesso informando quantos parceiros foram reativados                                              |

Ações Detalhadas - Inativar

| ID        | Requisito                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.43 | Ao clicar em "Inativar selecionados", o sistema deve exibir modal de confirmação com a quantidade de parceiros                      |
| RF-057.44 | Ao confirmar, o sistema deve alterar o status dos parceiros para "Inativa"                                                           |
| RF-057.45 | O sistema deve exibir mensagem de sucesso informando quantos parceiros foram inativados                                              |

Ações Detalhadas - Excluir

| ID        | Requisito                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RF-057.46 | Ao clicar em "Excluir", o sistema deve exibir modal de confirmação informando a quantidade de parceiros que serão excluídos         |
| RF-057.47 | Ao confirmar, o sistema deve realizar **soft delete** (marcar como excluído no banco de dados)                                      |
| RF-057.48 | Parceiros excluídos **não devem** aparecer em nenhuma aba da listagem                                                               |
| RF-057.49 | O sistema deve exibir mensagem de sucesso após exclusão                                                                              |
| RF-057.55 | Ao confirmar a exclusão, o sistema deve bloquear automaticamente o acesso de todos os Editores e Leitores vinculados ao parceiro excluído, sem excluir seus registros (RN-057.18)                      |

Colunas da Tabela

| Coluna             | Conteúdo                              | Ordenável | Observação                                    |
|--------------------|---------------------------------------|-----------|-----------------------------------------------|
| Checkbox           | ☐                                     | ❌         | Seleção múltipla                              |
| ID                 | ID numérico                           | ✅         | Ordenação padrão DESC                         |
| Razão Social       | Nome legal com logo/avatar            | ✅         | Ordena alfabeticamente                        |
| Nome Fantasia      | Nome comercial                        | ✅         | Ordena alfabeticamente                        |
| CNPJ               | Número formatado (XX.XXX.XXX/XXXX-XX) | ✅         | CNPJ único no sistema                         |
| E-mail Responsável | E-mail do responsável                 | ✅         | Ordena alfabeticamente                        |
| Status             | Badge visual colorido                 | ✅         | Ativa / Pendente / Suspensa / Inativa         |
| Qtd Atrações       | Número inteiro                        | ✅         | Total de atrações vinculadas e ativas         |
| Data de Cadastro   | DD/MM/AAAA HH:MM:SS                   | ✅         | Data do primeiro cadastro no sistema          |

Abas de Status

| Aba                    | Descrição                                     | Ações Disponíveis                                              |
|------------------------|-----------------------------------------------|----------------------------------------------------------------|
| Ativas                 | Parceiros com status ativo                    | Editar, Suspender, Inativar, Excluir                           |
| Pendente de Aprovação  | Parceiros aguardando aprovação administrativa | Aprovar, Rejeitar, Solicitar Documentação Pendente              |
| Suspensas              | Parceiros temporariamente bloqueados          | Editar, Reativar, Inativar, Excluir                            |
| Inativas               | Parceiros inativos ou rejeitados              | Editar, Reativar, Excluir                                      |
| Todas                  | Todos os parceiros (exceto excluídos)         | Editar, ações contextuais conforme status dos selecionados     |

Filtros Avançados (Botão Filtro)

| Filtro           | Tipo               | Opções / Formato                                    |
|------------------|--------------------|-----------------------------------------------------|
| Status           | Multi-select       | Ativa, Pendente de Aprovação, Suspensa, Inativa     |
| Data de Cadastro | Intervalo de datas | Data inicial - Data final                           |
| Cidade/UF        | Texto + select     | Cidade livre + UF (lista de estados)                |
| Qtd Atrações     | Faixa numérica     | Mínimo - Máximo                                     |
| Segmento         | Multi-select       | Museu, Parque, Restaurante, Hotel, Passeio, Evento, Outro |

Barra de Ações por Aba

| Aba                   | Ações                                                                                             |
|-----------------------|---------------------------------------------------------------------------------------------------|
| Ativas                | [Selecionados X] [Editar] [Suspender selecionados] [Inativar selecionados] [Excluir]              |
| Pendente de Aprovação | [Selecionados X] [Aprovar selecionados] [Rejeitar selecionados] [Solicitar Documentação Pendente]† |
| Suspensas             | [Selecionados X] [Editar] [Reativar selecionados] [Inativar selecionados] [Excluir]               |
| Inativas              | [Selecionados X] [Editar] [Reativar selecionados] [Excluir]                                       |
| Todas                 | [Selecionados X] [Editar] [Excluir] [ação contextual conforme status]*                            |

*O botão muda conforme o status dos parceiros selecionados
†"Solicitar Documentação Pendente" só fica habilitado quando exatamente 1 parceiro está selecionado (RF-057.50)

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                                                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-057.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                                                                                                                                                                                                                                                            |
| RN-057.02 | Ao aprovar um parceiro, o status é alterado para "Ativa" e um e-mail com credenciais de acesso ao Backoffice (usuário e senha temporária) é enviado ao responsável                                                                                                                                                                                                    |
| RN-057.03 | A rejeição de um parceiro exige preenchimento obrigatório do motivo; o motivo é enviado por e-mail ao responsável com instruções para recurso ou contato com o suporte                                                                                                                                                                                                |
| RN-057.04 | A suspensão de um parceiro bloqueia todos os Editores e Leitores vinculados, que ficam impedidos de acessar o Backoffice                                                                                                                                                                                                                                              |
| RN-057.05 | A reativação de um parceiro libera automaticamente todos os Editores e Leitores vinculados                                                                                                                                                                                                                                                                            |
| RN-057.06 | A exclusão é um **soft delete** — o registro é marcado como excluído no banco e não aparece em nenhuma aba da listagem                                                                                                                                                                                                                                                |
| RN-057.07 | O botão "Editar" só é habilitado quando **exatamente 1 parceiro** está selecionado                                                                                                                                                                                                                                                                                    |
| RN-057.08 | Um parceiro previamente aprovado que foi inativado pode ser reativado diretamente para "Ativa", sem necessidade de nova aprovação                                                                                                                                                                                                                                     |
| RN-057.09 | A busca deve ser realizada de forma case-insensitive por Razão Social, Nome Fantasia, CNPJ e e-mail do responsável                                                                                                                                                                                                                                                    |
| RN-057.10 | A ordenação padrão é por **ID decrescente** (mais recente primeiro)                                                                                                                                                                                                                                                                                                   |
| RN-057.11 | A paginação padrão exibe **10 registros** por página                                                                                                                                                                                                                                                                                                                  |
| RN-057.12 | O CNPJ deve ser único no sistema — não é permitido cadastrar dois parceiros com o mesmo CNPJ                                                                                                                                                                                                                                                                          |
| RN-057.13 | Quando um novo Parceiro Comercial realiza auto-cadastro via Portal (RF-053) e fica com status "Pendente de Aprovação", o sistema deve enviar notificação ao(s) Administrador(es) por e-mail e via notificação interna no Backoffice, informando que há um novo cadastro aguardando análise.                                                                            |
| RN-057.14 | Ao aprovar um parceiro, o sistema deve gerar automaticamente um **Contrato de Atração** com status "Rascunho" no módulo de Gestão de Contratos (RF-008), pré-preenchido com os dados cadastrais do parceiro (Razão Social, CNPJ, responsável cadastrado em RF-053). O Admin deve complementar o contrato com os dados da atração específica antes de enviá-lo ao DocuSign. |
| RN-057.15 | O Parceiro Comercial aprovado recebe status "Ativa" com acesso imediato ao Backoffice para fins de configuração e leitura. O status do Parceiro Comercial (Ativa/Inativa) dita apenas o seu direito de autenticação (login no Backoffice); a permissão de venda é controlada separadamente por um Substatus de Operação em cada atração vinculada: **"Bloqueado para Vendas"** (padrão, aplicado automaticamente na criação da atração — impede qualquer transação ou emissão de ingressos na API pública de vendas) e **"Liberado para Vendas"** (aplicado automaticamente apenas quando o Contrato de Atração correspondente atingir o status "Ativo" no módulo RF-008, com a confirmação de todas as assinaturas via DocuSign) |
| RN-057.16 | Para cadastro manual feito pelo Administrador via botão "Adicionar Parceiro" (ou via RF-007), o parceiro é criado diretamente com status "Ativa", sem passar pela fila de aprovação. Os Contratos de Atração devem ser gerados pelo Admin via botão "Adicionar Contrato" em RF-008 quando as atrações forem cadastradas.                                               |
| RN-057.17 | (Solicitação de Documentação) O Administrador pode, a qualquer momento durante a análise de um parceiro com status "Pendente de Aprovação", solicitar documentação ou informação complementar sem alterar o status do cadastro; o sistema envia notificação por e-mail ao responsável (que ainda não possui acesso ao Backoffice) e registra a solicitação no histórico do parceiro |
| RN-057.18 | (Exclusão e Vínculos) Ao excluir (soft delete) um Parceiro Comercial, todos os Editores e Leitores vinculados a ele têm seu acesso ao Backoffice bloqueado automaticamente, de forma análoga à suspensão (RN-057.04); os registros desses usuários são preservados para fins de auditoria e histórico, mas não podem mais autenticar enquanto o parceiro permanecer excluído |

Critérios de Aceitação

| ID        | Critério                                                             | Resultado Esperado                                                                                                                                             |
|-----------|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-057.01 | Acessar Gestão de Parceiros Comerciais como Administrador            | Tela exibida com aba "Ativas" selecionada e tabela de parceiros ativos carregada                                                                               |
| CA-057.02 | Buscar por Razão Social existente                                    | Lista filtrada exibindo apenas parceiros com a razão social buscada                                                                                            |
| CA-057.03 | Buscar por CNPJ completo ou parcial                                  | Lista filtrada exibindo apenas parceiros com o CNPJ correspondente                                                                                             |
| CA-057.04 | Aplicar filtro por Status "Suspensa" e Cidade                        | Lista exibe apenas parceiros suspensos da cidade informada                                                                                                     |
| CA-057.05 | Navegar para a aba "Pendente de Aprovação"                           | Lista atualiza exibindo apenas parceiros com status Pendente; barra de ações exibe Aprovar, Rejeitar e Solicitar Documentação Pendente                        |
| CA-057.06 | Clicar em uma linha da tabela (sem selecionar checkbox)              | Modal somente leitura abre com resumo do parceiro; campos não editáveis                                                                                        |
| CA-057.07 | Selecionar exatamente 1 parceiro via checkbox                        | Barra de ações exibe "Selecionados 1" com botão "Editar" habilitado                                                                                            |
| CA-057.08 | Selecionar 3 parceiros via checkbox                                  | Barra de ações exibe "Selecionados 3" com botão "Editar" **desabilitado**                                                                                      |
| CA-057.09 | Aprovar parceiro pendente                                            | Status alterado para "Ativa"; parceiro migra para aba "Ativas"; e-mail com credenciais enviado; Contrato de Atração com status "Rascunho" gerado em RF-008; atrações vinculadas permanecem com Substatus "Bloqueado para Vendas" até a ativação do contrato no DocuSign (RN-057.15)    |
| CA-057.10 | Tentar rejeitar parceiro sem preencher o motivo                      | Sistema exibe mensagem de erro e impede a confirmação                                                                                                          |
| CA-057.11 | Rejeitar parceiro com motivo preenchido                              | Status alterado para "Inativa"; e-mail com motivo enviado ao responsável; parceiro migra para "Inativas"                                                       |
| CA-057.12 | Suspender parceiro ativo                                             | Status alterado para "Suspensa"; parceiro migra para aba "Suspensas"; Editores e Leitores vinculados bloqueados                                                |
| CA-057.13 | Reativar parceiro suspenso                                           | Status alterado para "Ativa"; parceiro migra para aba "Ativas"; Editores e Leitores vinculados liberados                                                       |
| CA-057.14 | Inativar parceiro ativo                                              | Status alterado para "Inativa"; parceiro migra para aba "Inativas"                                                                                             |
| CA-057.15 | Reativar parceiro inativo (previamente aprovado)                     | Status alterado para "Ativa" diretamente, sem nova aprovação; Editores e Leitores vinculados liberados                                                         |
| CA-057.16 | Excluir parceiro com confirmação                                     | Parceiro removido de todas as abas; Editores e Leitores vinculados têm o acesso ao Backoffice bloqueado (RN-057.18); mensagem de sucesso exibida              |
| CA-057.17 | Alterar paginação para 50                                            | Lista exibe até 50 registros por página                                                                                                                        |
| CA-057.18 | Navegar para a próxima página                                        | Lista exibe os próximos registros conforme paginação                                                                                                           |
| CA-057.19 | Clicar em "Adicionar Parceiro"                                       | Modal ou tela de cadastro de novo parceiro comercial é aberta                                                                                                  |
| CA-057.20 | Selecionar 1 parceiro pendente e clicar em "Solicitar Documentação Pendente", informando a descrição da pendência | Status permanece "Pendente de Aprovação"; e-mail enviado ao responsável com a pendência descrita; solicitação registrada no histórico do parceiro             |
| CA-057.21 | Tentar confirmar "Solicitar Documentação Pendente" sem informar a descrição da pendência | Sistema exibe mensagem de erro e impede a confirmação                                                                                                          |

Protótipo/Wireframe

Figura - WF-061 - Gestão de Parceiros Comerciais.png (a definir)
