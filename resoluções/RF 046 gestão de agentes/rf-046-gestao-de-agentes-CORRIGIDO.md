### 3.46 Gestão de Agentes

**ID:** RF-046

Módulo: Gestão de Agentes

Perfis com Acesso: Administrador (visão global); Agência (apenas seus próprios agentes)

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo para gerenciar os Agentes (revendedores individuais) do sistema. O Administrador visualiza e gerencia todos os agentes de todas as agências. O perfil Agência gerencia apenas seus próprios agentes. Permite vincular, criar, editar, inativar/ativar, desvincular e transferir agentes entre agências (Admin only). O status do agente é sempre subordinado ao status da agência à qual está vinculado: ao inativar, reativar ou excluir uma agência (RF-044), os agentes vinculados sofrem automaticamente o efeito em cascata correspondente, conforme detalhado nas Regras de Negócio deste módulo.

Requisitos Detalhados

Estrutura Geral da Tela — Visão do Administrador

| ID        | Requisito                                                                                                    |
|-----------|--------------------------------------------------------------------------------------------------------------|
| RF-046.01 | O sistema deve exibir o título "Gestão de Agentes"                                                           |
| RF-046.02 | O sistema deve exibir campo de pesquisa por texto (busca por nome, CPF ou e-mail)                            |
| RF-046.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                                  |
| RF-046.04 | O sistema deve exibir botão "Adicionar Agente" para cadastrar ou vincular novo agente                        |
| RF-046.05 | O sistema deve exibir abas para filtrar por status: "Ativos", "Inativos", "Todos"                            |
| RF-046.06 | O sistema deve exibir a aba "Ativos" selecionada por padrão                                                  |

Tabela de Agentes — Visão do Administrador

| ID        | Requisito                                                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------|
| RF-046.07 | O sistema deve exibir tabela com os agentes cadastrados conforme a aba selecionada                                                    |
| RF-046.08 | A tabela deve exibir as colunas: Checkbox, ID, Nome, CPF (mascarado), E-mail, Agência Vinculada, Qtd Atrações, Status, Data Cadastro  |
| RF-046.09 | A coluna CPF deve exibir o valor mascarado no formato `XXX.XXX.XXX-**`                                                                |
| RF-046.10 | A coluna Status deve exibir badge visual indicando Ativo, Inativo ou **Inativo (Agência Bloqueada)** quando a inatividade for decorrente do bloqueio em cascata da agência vinculada |
| RF-046.11 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                                                 |
| RF-046.12 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização somente leitura                        |

Seleção e Ações em Massa — Visão do Administrador

| ID        | Requisito                                                                                                              |
|-----------|------------------------------------------------------------------------------------------------------------------------|
| RF-046.13 | O sistema deve exibir checkbox na primeira coluna para seleção de agentes                                              |
| RF-046.14 | O sistema deve permitir selecionar múltiplos agentes via checkbox                                                      |
| RF-046.15 | Ao selecionar um ou mais agentes, o sistema deve exibir barra de ações contextual com contador "Selecionados X"        |
| RF-046.16 | Na aba "Ativos", a barra de ações deve exibir: "Editar", "Inativar", "Excluir", "Transferir para outra Agência"        |
| RF-046.17 | Na aba "Inativos", a barra de ações deve exibir: "Editar", "Ativar", "Excluir"; os botões "Ativar" e "Editar" devem estar desabilitados para agentes cuja inatividade decorra do bloqueio em cascata de uma agência inativa ou suspensa (RN-046.14) |
| RF-046.18 | O botão "Editar" deve estar habilitado apenas quando **1 agente** estiver selecionado                                  |
| RF-046.19 | Os botões "Inativar", "Ativar", "Excluir" e "Transferir" devem funcionar para múltiplos agentes selecionados           |

Paginação

| ID        | Requisito                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------|
| RF-046.20 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100   |
| RF-046.21 | O sistema deve exibir indicador de registros: "X a Y de Z"                                       |
| RF-046.22 | O sistema deve exibir navegação: primeira página, anterior, página atual, próxima, última página |

Estrutura Geral — Visão da Agência

| ID        | Requisito                                                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------|
| RF-046.23 | O perfil Agência deve acessar o módulo via menu "Meus Agentes"                                                                        |
| RF-046.24 | A tabela deve ser filtrada automaticamente para exibir apenas os agentes vinculados à agência autenticada                             |
| RF-046.25 | O perfil Agência deve ter as seguintes ações disponíveis: adicionar/vincular, visualizar, editar, inativar/ativar, desvincular agente  |
| RF-046.26 | O perfil Agência **não deve** ter a opção de excluir agentes do sistema                                                               |
| RF-046.27 | O perfil Agência **não deve** ter a opção de transferir agentes para outra agência                                                    |

Modal de Cadastro/Edição

| ID        | Requisito                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-046.28 | O modal de cadastro/edição deve exibir campo para foto de perfil do agente                                                                        |
| RF-046.29 | O modal deve exibir campo Nome completo (obrigatório)                                                                                             |
| RF-046.30 | O modal deve exibir campo CPF (obrigatório, único no sistema, com validação de formato e dígito verificador). CPFs de agentes em soft delete não bloqueiam novo cadastro: o sistema deve permitir um novo cadastro com o mesmo CPF, sujeito à análise do Administrador (RN-046.16) |
| RF-046.31 | O modal deve exibir campo E-mail (obrigatório, único no sistema, utilizado como login)                                                            |
| RF-046.32 | O modal deve exibir campo Telefone                                                                                                                |
| RF-046.33 | O modal deve exibir campo Idioma padrão com opções: Português, English, Español                                                                   |
| RF-046.34 | No cadastro, o modal deve exibir campo Senha                                                                                                      |
| RF-046.35 | O campo Agência Vinculada deve permitir ao Administrador selecionar qualquer agência; ao perfil Agência deve ser fixado na própria agência         |
| RF-046.36 | O modal deve exibir campo Atrações Autorizadas com checkboxes para definir quais atrações o agente pode comercializar                             |
| RF-046.37 | O modal deve exibir campo Status com opções Ativo/Inativo                                                                                         |

Ação Transferir Agente (Admin only)

| ID        | Requisito                                                                                                                             |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------|
| RF-046.38 | O Administrador deve poder selecionar um ou mais agentes (ativos ou inativos) e acionar a ação "Transferir para outra Agência". Caso algum agente selecionado esteja Inativo, o sistema deve, ao concluir a transferência, reativá-lo automaticamente na agência de destino, desde que a agência de destino esteja com status "Ativa" e contrato vigente no RF-008 — eliminando a necessidade de reativar manualmente antes de transferir |
| RF-046.39 | O sistema deve exibir modal para seleção da agência de destino, listando apenas agências com status "Ativa" |
| RF-046.40 | O sistema deve exibir modal de confirmação com nome dos agentes, status atual de cada um (Ativo/Inativo) e agência de destino antes de concluir a transferência |
| RF-046.41 | Ao confirmar a transferência, o vínculo do agente deve ser atualizado para a nova agência. A partir da confirmação, o agente passa a vender exclusivamente produtos/atrações autorizadas pela nova agência; o vínculo com a agência de origem é integralmente desfeito para fins de operação |
| RF-046.42 | O histórico de comissionamento gerado antes da transferência deve permanecer vinculado à agência de origem, de forma irrevogável (vide RN-046.09 e RN-048.13) |
| RF-046.43 | O comissionamento gerado após a transferência deve ser vinculado à nova agência                                                       |
| RF-046.44 | Vendas realizadas pelo agente antes da transferência permanecem contabilizadas na agência de origem para todos os fins (relatórios, estatísticas e comissionamento); a transferência não retroage sobre vendas já registradas |

Colunas da Tabela

| Coluna            | Conteúdo                        | Ordenável | Observação                         |
|-------------------|----------------------------------|-----------|------------------------------------|
| Checkbox          | ☐                               | ❌         | Seleção múltipla                   |
| ID                | ID numérico                     | ✅         | Ordenação padrão DESC              |
| Nome              | Nome completo do agente         | ✅         | Ordena por nome                    |
| CPF               | `XXX.XXX.XXX-**` (mascarado)    | ❌         | Nunca exibido completo na listagem |
| E-mail            | E-mail de login                 | ✅         | —                                  |
| Agência Vinculada | Nome da agência                 | ✅         | Apenas na visão do Administrador   |
| Qtd Atrações      | Número inteiro                  | ✅         | Atrações autorizadas ao agente     |
| Status            | Badge Ativo / Inativo / Inativo (Agência Bloqueada) | ✅ | Distingue inativação manual de bloqueio em cascata |
| Data Cadastro     | DD/MM/AAAA                      | ✅         | —                                  |

Abas de Status

| Aba      | Descrição                           | Ações Disponíveis (Admin)                                 | Ações Disponíveis (Agência)          |
|----------|--------------------------------------|-------------------------------------------------------------|----------------------------------------|
| Ativos   | Agentes com status ativo            | Editar, Inativar, Excluir, Transferir para outra Agência  | Editar, Inativar, Desvincular        |
| Inativos | Agentes com status inativo (manual ou por bloqueio em cascata da agência) | Editar, Ativar, Excluir, Transferir (reativa na nova agência) | Editar, Ativar (bloqueado se a inativação for por cascata da agência) |
| Todos    | Todos os agentes (exceto excluídos) | Editar, Excluir, Inativar/Ativar                          | Editar, Inativar/Ativar, Desvincular |

Filtros Avançados (Botão Filtro)

| Filtro            | Tipo               | Opções / Formato          |
|-------------------|--------------------|---------------------------|
| Agência Vinculada | Multi-select       | Lista de agências ativas  |
| Status            | Select             | Ativo, Inativo, Inativo (Agência Bloqueada) |
| Data de Cadastro  | Intervalo de datas | Data inicial - Data final |

Barra de Ações por Perfil

| Perfil         | Aba      | Ações                                                                              |
|----------------|----------|--------------------------------------------------------------------------------------|
| Administrador  | Ativos   | [Selecionados X] [Editar] [Inativar] [Excluir] [Transferir para outra Agência]     |
| Administrador  | Inativos | [Selecionados X] [Editar] [Ativar] [Excluir] [Transferir para outra Agência]        |
| Agência        | Ativos   | [Selecionados X] [Editar] [Inativar] [Desvincular]                                 |
| Agência        | Inativos | [Selecionados X] [Editar] [Ativar]                                                 |

O botão "Editar" é habilitado apenas quando exatamente 1 agente está selecionado. Para agentes inativados por bloqueio em cascata da agência, os botões "Ativar" e "Editar" ficam desabilitados até a agência ser reativada ou até o agente ser transferido para outra agência ativa.

Regras de Negócio

| ID        | Regra                                                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| RN-046.01 | O perfil **Administrador** visualiza e gerencia todos os agentes do sistema, independentemente da agência                                  |
| RN-046.02 | O perfil **Agência** visualiza e gerencia apenas os agentes vinculados à sua própria agência                                               |
| RN-046.03 | Um agente deve estar vinculado a **apenas uma agência** por vez                                                                            |
| RN-046.04 | Agente com status **Inativo** não pode realizar vendas nem ser selecionado em transações                                                   |
| RN-046.05 | Ao desvincular um agente (ação do perfil Agência), o status do agente é automaticamente alterado para **Inativo** até novo vínculo         |
| RN-046.06 | O campo **e-mail é único** no sistema e utilizado como credencial de login do agente                                                       |
| RN-046.07 | O perfil **Agência** pode desvincular agentes, mas **não pode** excluí-los do sistema                                                      |
| RN-046.08 | Apenas o perfil **Administrador** pode transferir um agente de uma agência para outra. O Administrador pode selecionar agentes ativos ou inativos para a operação; agentes inativos são automaticamente reativados na agência de destino ao final da transferência (RF-046.38), eliminando a necessidade de reativação manual prévia |
| RN-046.09 | O histórico de comissões gerado antes de uma transferência **permanece vinculado à agência de origem**, de forma irrevogável, mesmo após o agente ser transferido (consistente com RN-048.13 — Imutabilidade do Vínculo Financeiro) |
| RN-046.10 | O **CPF deve ser mascarado** na listagem (`XXX.XXX.XXX-**`), sendo visível completo apenas no modal de edição/visualização                 |
| RN-046.11 | A busca por texto deve ser **case-insensitive** e operar sobre nome, CPF e e-mail                                                          |
| RN-046.12 | A paginação padrão exibe **10 registros** por página                                                                                       |
| RN-046.13 | A **senha do agente não deve** ser exibida em nenhuma tela após o cadastro                                                                 |
| RN-046.14 | Quando o Administrador **inativar** uma agência (RF-044), o sistema deve alterar automaticamente, **em cascata**, o status de todos os agentes vinculados para "Inativo", bloqueando imediatamente seus logins no aplicativo/portal e impedindo novas vendas. Esses agentes ficam marcados na interface como "Inativo (Agência Bloqueada)" para distinguir da inativação manual |
| RN-046.15 | Quando o Administrador **reativar** uma agência (RF-044) e o Contrato de Agência estiver com status "Ativo" no RF-008, o sistema deve restabelecer automaticamente, **em cascata**, o status "Ativo" de todos os agentes que estavam inativos exclusivamente em decorrência do bloqueio da agência (RN-046.14). Agentes que já estavam inativados manualmente antes do bloqueio da agência **não** são reativados automaticamente — devem ser reativados individualmente pelo Administrador ou pela Agência |
| RN-046.16 | Quando uma agência for excluída (soft delete, RF-044.46), o sistema deve aplicar **soft delete em cascata** a todos os agentes vinculados, registrando o vínculo de origem para fins de histórico e auditoria. Agentes em soft delete não aparecem em nenhuma busca, listagem ou tela de relatório do sistema. O CPF de um agente em soft delete pode ser reutilizado em novo cadastro, sujeito à análise do Administrador para evitar fraude ou duplicidade indevida |
| RN-046.17 | A exclusão (soft delete) de um agente preserva integralmente seu histórico financeiro e estatístico de vendas (comissões geradas, vendas realizadas), que permanece consultável via relatórios de auditoria mesmo após a exclusão |
| RN-046.18 | As comissões acumuladas e pendentes de pagamento ("a pagar") de agentes vinculados a uma agência inativada **não ficam congeladas**: o sistema deve continuar permitindo o processamento e o pagamento dessas comissões normalmente, mesmo com a agência em status "Inativa", desde que o período de apuração já esteja fechado (RF-048) |

Critérios de Aceitação

| ID        | Critério                                                           | Resultado Esperado                                                                                   |
|-----------|----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| CA-046.01 | Acessar Gestão de Agentes como Administrador                       | Tela exibida com aba "Ativos" selecionada e lista global de todos os agentes                         |
| CA-046.02 | Acessar "Meus Agentes" como Agência                                | Tela exibida com aba "Ativos" selecionada e lista restrita aos agentes da agência autenticada         |
| CA-046.03 | Pesquisar por nome de agente                                       | Lista filtrada exibindo apenas agentes cujo nome contém o texto digitado (case-insensitive)          |
| CA-046.04 | Pesquisar por CPF (parcial ou completo)                            | Lista filtrada exibindo agentes cujo CPF corresponde ao valor digitado                               |
| CA-046.05 | Aplicar filtro por agência vinculada                               | Lista exibe apenas agentes da(s) agência(s) selecionada(s) no filtro                                |
| CA-046.06 | Clicar na aba "Inativos"                                           | Lista atualiza exibindo apenas agentes com status inativo                                            |
| CA-046.07 | Clicar na aba "Todos"                                              | Lista atualiza exibindo agentes ativos e inativos                                                    |
| CA-046.08 | Clicar em uma linha da tabela (sem usar checkbox)                  | Modal de visualização abre com todos os campos em modo somente leitura                               |
| CA-046.09 | Selecionar 1 agente via checkbox (aba Ativos — Admin)              | Barra de ações exibe: "Selecionados 1", Editar (habilitado), Inativar, Excluir, Transferir           |
| CA-046.10 | Selecionar 3 agentes via checkbox (aba Ativos — Admin)             | Barra de ações exibe: "Selecionados 3", botão Editar **desabilitado**                                |
| CA-046.11 | Confirmar inativação em massa (Admin)                              | Agentes selecionados movidos para aba "Inativos" + mensagem de sucesso exibida                       |
| CA-046.12 | Confirmar ativação em massa (Admin — aba Inativos)                 | Agentes selecionados movidos para aba "Ativos" + mensagem de sucesso exibida                         |
| CA-046.13 | Transferir agente ativo para outra agência (Admin)                 | Modal de seleção de agência exibido → modal de confirmação → vínculo atualizado + mensagem de sucesso |
| CA-046.14 | Desvincular agente (Agência)                                       | Agente removido da lista da agência + status alterado para Inativo + mensagem de sucesso             |
| CA-046.15 | Tentar cadastrar agente com e-mail já existente                    | Sistema exibe mensagem de erro "E-mail já cadastrado no sistema"                                     |
| CA-046.16 | Verificar agente inativo em fluxo de venda                         | Agente inativo não aparece disponível para seleção em nenhuma transação de venda                     |
| CA-046.17 | Alterar paginação para 50                                          | Lista atualiza exibindo até 50 registros por página                                                  |
| CA-046.18 | Administrador inativa uma agência com 5 agentes vinculados (RF-044) | Os 5 agentes têm o status alterado automaticamente para "Inativo (Agência Bloqueada)"; login bloqueado imediatamente no app/portal; agentes não aparecem disponíveis para venda |
| CA-046.19 | Administrador reativa uma agência cujo contrato está ativo no RF-008, e que possuía 5 agentes bloqueados por cascata e 1 agente já inativado manualmente antes do bloqueio | Os 5 agentes bloqueados por cascata retornam automaticamente para "Ativo"; o agente inativado manualmente permanece "Inativo", exigindo reativação individual |
| CA-046.20 | Transferir um agente **inativo** para outra agência ativa (Admin)  | Sistema exibe aviso de que o agente será reativado na nova agência; ao confirmar, agente é transferido e automaticamente reativado, sem necessidade de ativá-lo manualmente antes |
| CA-046.21 | Verificar vendas realizadas por um agente antes de sua transferência para outra agência | Vendas permanecem contabilizadas e vinculadas à agência de origem em relatórios e estatísticas; comissões dessas vendas seguem a RN-046.09 |
| CA-046.22 | Excluir (soft delete) um agente com histórico de vendas e comissões  | Agente removido das listagens padrão; histórico financeiro e estatístico preservado e consultável via relatório de auditoria; CPF do agente disponível para novo cadastro sujeito à análise do Administrador |
| CA-046.23 | Excluir (soft delete) uma agência com agentes vinculados (RF-044)   | Todos os agentes vinculados sofrem soft delete em cascata; não aparecem em buscas, listagens ou relatórios de Gestão de Agentes; vínculo de origem preservado para auditoria |
| CA-046.24 | Verificar pagamento de comissão acumulada de agente vinculado a agência inativa, em período já fechado | Sistema processa e efetua o pagamento normalmente, mesmo com a agência em status "Inativa" |

Protótipo/Wireframe

Figura - WF-050 - Gestão de Agentes.png (a definir)
