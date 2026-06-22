### 3.44 Gestão de Agências - Administrador

**ID:** RF-044

Módulo: Gestão de Agências

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Tela de listagem e gerenciamento de todas as agências de turismo cadastradas no sistema. O Administrador pode buscar, filtrar, visualizar, aprovar, rejeitar, suspender, reativar, inativar e excluir agências, além de cadastrar novas por meio do botão "Adicionar Agência".

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------|
| RF-044.01 | O sistema deve exibir o título "Gestão de Agências" com subtítulo "Gerencie as agências de turismo cadastradas no sistema"   |
| RF-044.02 | O sistema deve exibir campo de busca por texto (busca por Nome Fantasia, CNPJ e e-mail do responsável)                      |
| RF-044.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                                                  |
| RF-044.04 | O sistema deve exibir botão "Adicionar Agência" para cadastrar nova agência                                                  |
| RF-044.05 | O sistema deve exibir abas para filtrar por status: "Ativas", "Pendente de Aprovação", "Suspensas", "Inativas", "Todas"     |
| RF-044.06 | O sistema deve exibir a aba "Ativas" selecionada por padrão                                                                  |

Tabela de Agências

| ID        | Requisito                                                                                                                           |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| RF-044.07 | O sistema deve exibir tabela com as agências cadastradas conforme a aba selecionada                                                 |
| RF-044.08 | A tabela deve exibir as colunas: Checkbox, ID, Nome Fantasia, CNPJ, E-mail Responsável, Status, Qtd Agentes, Data de Cadastro       |
| RF-044.09 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                                               |
| RF-044.10 | A ordenação padrão deve ser por ID decrescente (mais recente primeiro)                                                              |
| RF-044.11 | A coluna Status deve exibir badge visual com cor diferenciada por situação: Ativa (verde), Pendente (amarelo), Suspensa (laranja), Inativa (cinza) |
| RF-044.12 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização somente leitura com resumo da agência |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                                       |
|-----------|---------------------------------------------------------------------------------------------------------------------------------|
| RF-044.13 | O sistema deve exibir checkbox na primeira coluna para seleção de agências                                                      |
| RF-044.14 | O sistema deve permitir selecionar múltiplas agências via checkbox                                                              |
| RF-044.15 | Ao selecionar uma ou mais agências, o sistema deve exibir barra de ações com contador "Selecionados X"                          |
| RF-044.16 | Na aba "Pendente de Aprovação", a barra de ações deve exibir: "Aprovar selecionadas", "Rejeitar selecionadas"                   |
| RF-044.17 | Na aba "Ativas", a barra de ações deve exibir: "Editar", "Suspender selecionadas", "Inativar selecionadas", "Excluir"           |
| RF-044.18 | Na aba "Suspensas", a barra de ações deve exibir: "Editar", "Reativar selecionadas", "Inativar selecionadas", "Excluir"         |
| RF-044.19 | Na aba "Inativas", a barra de ações deve exibir: "Editar", "Reativar selecionadas", "Excluir"                                   |
| RF-044.20 | O botão "Editar" deve estar habilitado apenas quando **exatamente 1 agência** estiver selecionada                               |
| RF-044.21 | Os botões de ação em massa devem funcionar para múltiplas agências selecionadas                                                  |

Paginação

| ID        | Requisito                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------|
| RF-044.22 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100    |
| RF-044.23 | O sistema deve exibir indicador de registros: "X a Y de Z"                                        |
| RF-044.24 | O sistema deve exibir navegação: primeira página, anterior, página atual, próxima, última página   |

Ações Detalhadas - Aprovar

| ID        | Requisito                                                                                                           |
|-----------|---------------------------------------------------------------------------------------------------------------------|
| RF-044.25 | Ao clicar em "Aprovar selecionadas", o sistema deve exibir modal de confirmação com a quantidade de agências         |
| RF-044.26 | Ao confirmar, o sistema deve alterar o status das agências para "Ativa"                                             |
| RF-044.27 | O sistema deve enviar e-mail de boas-vindas ao responsável de cada agência aprovada                                 |
| RF-044.28 | O sistema deve exibir mensagem de sucesso informando quantas agências foram aprovadas                               |

Ações Detalhadas - Rejeitar

| ID        | Requisito                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------|
| RF-044.29 | Ao clicar em "Rejeitar selecionadas", o sistema deve exibir modal com campo de motivo obrigatório                               |
| RF-044.30 | O sistema deve impedir a confirmação da rejeição se o campo de motivo estiver vazio, exibindo mensagem de erro                  |
| RF-044.31 | Ao confirmar, o sistema deve alterar o status das agências para "Inativa"                                                       |
| RF-044.32 | O sistema deve enviar e-mail ao responsável de cada agência rejeitada informando o motivo da rejeição                           |
| RF-044.33 | O sistema deve exibir mensagem de sucesso informando quantas agências foram rejeitadas                                          |

Ações Detalhadas - Suspender

| ID        | Requisito                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------|
| RF-044.34 | Ao clicar em "Suspender selecionadas", o sistema deve exibir modal de confirmação com campo de motivo opcional                  |
| RF-044.35 | Ao confirmar, o sistema deve alterar o status das agências para "Suspensa"                                                      |
| RF-044.36 | Todos os agentes vinculados às agências suspensas devem ter suas contas bloqueadas (não podem realizar vendas)                  |
| RF-044.37 | O sistema deve exibir mensagem de sucesso informando quantas agências foram suspensas                                           |

Ações Detalhadas - Reativar

| ID        | Requisito                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------|
| RF-044.38 | Ao clicar em "Reativar selecionadas", o sistema deve exibir modal de confirmação com a quantidade de agências                   |
| RF-044.39 | Ao confirmar, o sistema deve alterar o status das agências para "Ativa"                                                         |
| RF-044.40 | Todos os agentes vinculados às agências reativadas devem ter seus acessos restabelecidos                                        |
| RF-044.41 | O sistema deve exibir mensagem de sucesso informando quantas agências foram reativadas                                          |

Ações Detalhadas - Inativar

| ID        | Requisito                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------|
| RF-044.42 | Ao clicar em "Inativar selecionadas", o sistema deve exibir modal de confirmação com a quantidade de agências                   |
| RF-044.43 | Ao confirmar, o sistema deve alterar o status das agências para "Inativa"                                                       |
| RF-044.44 | O sistema deve exibir mensagem de sucesso informando quantas agências foram inativadas                                          |

Ações Detalhadas - Excluir

| ID        | Requisito                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------|
| RF-044.45 | Ao clicar em "Excluir", o sistema deve exibir modal de confirmação informando a quantidade de agências que serão excluídas      |
| RF-044.46 | Ao confirmar, o sistema deve realizar **soft delete** (marcar como excluída no banco de dados)                                  |
| RF-044.47 | Agências excluídas **não devem** aparecer em nenhuma aba da listagem                                                            |
| RF-044.48 | O sistema deve exibir mensagem de sucesso após exclusão                                                                         |

Colunas da Tabela

| Coluna             | Conteúdo                              | Ordenável | Observação                                        |
|--------------------|---------------------------------------|-----------|---------------------------------------------------|
| Checkbox           | ☐                                     | ❌         | Seleção múltipla                                  |
| ID                 | ID numérico                           | ✅         | Ordenação padrão DESC                             |
| Nome Fantasia      | Nome comercial da agência             | ✅         | Ordena alfabeticamente                            |
| CNPJ               | Número formatado (XX.XXX.XXX/XXXX-XX) | ✅         | CNPJ único no sistema                             |
| E-mail Responsável | E-mail do responsável legal           | ✅         | Ordena alfabeticamente                            |
| Status             | Badge visual colorido                 | ✅         | Ativa / Pendente / Suspensa / Inativa             |
| Qtd Agentes        | Número inteiro                        | ✅         | Total de agentes vinculados e ativos              |
| Data de Cadastro   | DD/MM/AAAA HH:MM:SS                   | ✅         | Data do primeiro cadastro no sistema              |

Abas de Status

| Aba                    | Descrição                                    | Ações Disponíveis                                              |
|------------------------|----------------------------------------------|----------------------------------------------------------------|
| Ativas                 | Agências com status ativo                    | Editar, Suspender, Inativar, Excluir                           |
| Pendente de Aprovação  | Agências aguardando aprovação administrativa | Aprovar, Rejeitar                                              |
| Suspensas              | Agências temporariamente bloqueadas          | Editar, Reativar, Inativar, Excluir                            |
| Inativas               | Agências inativas ou rejeitadas              | Editar, Reativar, Excluir                                      |
| Todas                  | Todas as agências (exceto excluídas)         | Editar, ações contextuais conforme status dos selecionados     |

Filtros Avançados (Botão Filtro)

| Filtro           | Tipo               | Opções / Formato                              |
|------------------|--------------------|-----------------------------------------------|
| Status           | Multi-select       | Ativa, Pendente de Aprovação, Suspensa, Inativa |
| Data de Cadastro | Intervalo de datas | Data inicial - Data final                     |
| Cidade/UF        | Texto + select     | Cidade livre + UF (lista de estados)          |
| Qtd Agentes      | Faixa numérica     | Mínimo - Máximo                               |

Barra de Ações por Aba

| Aba                   | Ações                                                                           |
|-----------------------|---------------------------------------------------------------------------------|
| Ativas                | [Selecionados X] [Editar] [Suspender selecionadas] [Inativar selecionadas] [Excluir] |
| Pendente de Aprovação | [Selecionados X] [Aprovar selecionadas] [Rejeitar selecionadas]                 |
| Suspensas             | [Selecionados X] [Editar] [Reativar selecionadas] [Inativar selecionadas] [Excluir] |
| Inativas              | [Selecionados X] [Editar] [Reativar selecionadas] [Excluir]                     |
| Todas                 | [Selecionados X] [Editar] [Excluir] [ação contextual conforme status]*          |

O botão muda conforme o status das agências selecionadas

Regras de Negócio

| ID        | Regra                                                                                                                               |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| RN-044.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                          |
| RN-044.02 | Ao aprovar uma agência, o status é alterado para "Ativa" e um e-mail de boas-vindas é enviado ao responsável                        |
| RN-044.03 | A rejeição de uma agência exige preenchimento obrigatório do motivo; o motivo é enviado por e-mail ao responsável                   |
| RN-044.04 | A suspensão de uma agência bloqueia todos os agentes vinculados, que ficam impedidos de realizar vendas                             |
| RN-044.05 | A reativação de uma agência libera automaticamente todos os agentes vinculados                                                      |
| RN-044.06 | A exclusão é um **soft delete** — o registro é marcado como excluído no banco e não aparece em nenhuma aba da listagem              |
| RN-044.07 | O botão "Editar" só é habilitado quando **exatamente 1 agência** está selecionada                                                   |
| RN-044.08 | Uma agência previamente aprovada que foi inativada pode ser reativada diretamente para "Ativa", sem necessidade de nova aprovação   |
| RN-044.09 | A busca deve ser realizada de forma case-insensitive por Nome Fantasia, CNPJ e e-mail do responsável                               |
| RN-044.10 | A ordenação padrão é por **ID decrescente** (mais recente primeiro)                                                                 |
| RN-044.11 | A paginação padrão exibe **10 registros** por página                                                                                |
| RN-044.12 | O CNPJ deve ser único no sistema — não é permitido cadastrar duas agências com o mesmo CNPJ                                         |
| RN-044.13 | Quando uma nova agência realiza auto-cadastro via Portal e fica com status "Pendente de Aprovação", o sistema deve enviar notificação ao(s) Administrador(es) por e-mail e via notificação interna no Backoffice, informando que há um novo cadastro aguardando análise. |
| RN-044.14 | Ao aprovar uma agência, o sistema deve gerar automaticamente um rascunho de **Contrato de Agência** pré-preenchido no módulo de Gestão de Contratos (RF-008), com os dados cadastrados na RF-045 (razão social, CNPJ, responsável, dados bancários). O contrato é criado com status "Aguardando Envio", pronto para revisão e envio ao DocuSign pelo Administrador. |
| RN-044.15 | A agência aprovada **não pode operar** (seus agentes não podem realizar vendas) enquanto o Contrato de Agência não atingir o status "Ativo" no módulo RF-008, ou seja, enquanto todas as assinaturas via DocuSign não forem coletadas. |
| RN-044.16 | Para cadastro manual feito pelo Administrador via botão "Adicionar Agência", o sistema também gera automaticamente o rascunho de contrato pré-preenchido ao salvar o cadastro, seguindo o mesmo fluxo do auto-cadastro (RF-008 → DocuSign → Ativo). |

Critérios de Aceitação

| ID        | Critério                                                              | Resultado Esperado                                                                              |
|-----------|-----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| CA-044.01 | Acessar Gestão de Agências como Administrador                         | Tela exibida com aba "Ativas" selecionada e tabela de agências ativas carregada                 |
| CA-044.02 | Buscar por Nome Fantasia existente                                     | Lista filtrada exibindo apenas agências com o nome buscado                                      |
| CA-044.03 | Buscar por CNPJ completo ou parcial                                   | Lista filtrada exibindo apenas agências com o CNPJ correspondente                              |
| CA-044.04 | Aplicar filtro por Status "Suspensa" e Cidade                         | Lista exibe apenas agências suspensas da cidade informada                                       |
| CA-044.05 | Navegar para a aba "Pendente de Aprovação"                            | Lista atualiza exibindo apenas agências com status Pendente; barra de ações exibe Aprovar e Rejeitar |
| CA-044.06 | Clicar em uma linha da tabela (sem selecionar checkbox)               | Modal somente leitura abre com resumo da agência; campos não editáveis                         |
| CA-044.07 | Selecionar exatamente 1 agência via checkbox                          | Barra de ações exibe "Selecionados 1" com botão "Editar" habilitado                             |
| CA-044.08 | Selecionar 3 agências via checkbox                                    | Barra de ações exibe "Selecionados 3" com botão "Editar" **desabilitado**                       |
| CA-044.09 | Aprovar agência pendente                                              | Status alterado para "Ativa"; agência migra para aba "Ativas"; e-mail de boas-vindas enviado   |
| CA-044.10 | Tentar rejeitar agência sem preencher o motivo                        | Sistema exibe mensagem de erro e impede a confirmação                                           |
| CA-044.11 | Rejeitar agência com motivo preenchido                                | Status alterado para "Inativa"; e-mail com motivo enviado ao responsável; agência migra para "Inativas" |
| CA-044.12 | Suspender agência ativa                                               | Status alterado para "Suspensa"; agência migra para aba "Suspensas"; agentes vinculados bloqueados |
| CA-044.13 | Reativar agência suspensa                                             | Status alterado para "Ativa"; agência migra para aba "Ativas"; agentes vinculados liberados     |
| CA-044.14 | Inativar agência ativa                                                | Status alterado para "Inativa"; agência migra para aba "Inativas"                              |
| CA-044.15 | Reativar agência inativa (previamente aprovada)                       | Status alterado para "Ativa" diretamente, sem nova aprovação; agentes vinculados liberados      |
| CA-044.16 | Excluir agência com confirmação                                       | Agência removida de todas as abas; mensagem de sucesso exibida                                  |
| CA-044.17 | Alterar paginação para 50                                             | Lista exibe até 50 registros por página                                                         |
| CA-044.18 | Navegar para a próxima página                                         | Lista exibe os próximos registros conforme paginação                                            |
| CA-044.19 | Clicar em "Adicionar Agência"                                         | Modal ou tela de cadastro de nova agência é aberta                                              |

Protótipo/Wireframe

Figura - WF-048 - Gestão de Agências.png (a definir)
