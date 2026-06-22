### 3.46 Gestão de Agentes

**ID:** RF-046

Módulo: Gestão de Agentes

Perfis com Acesso: Administrador (visão global); Agência (apenas seus próprios agentes)

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo para gerenciar os Agentes (revendedores individuais) do sistema. O Administrador visualiza e gerencia todos os agentes de todas as agências. O perfil Agência gerencia apenas seus próprios agentes. Permite vincular, criar, editar, inativar/ativar, desvincular e transferir agentes entre agências (Admin only).

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
| RF-046.10 | A coluna Status deve exibir badge visual indicando Ativo ou Inativo                                                                   |
| RF-046.11 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                                                 |
| RF-046.12 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização somente leitura                        |

Seleção e Ações em Massa — Visão do Administrador

| ID        | Requisito                                                                                                              |
|-----------|------------------------------------------------------------------------------------------------------------------------|
| RF-046.13 | O sistema deve exibir checkbox na primeira coluna para seleção de agentes                                              |
| RF-046.14 | O sistema deve permitir selecionar múltiplos agentes via checkbox                                                      |
| RF-046.15 | Ao selecionar um ou mais agentes, o sistema deve exibir barra de ações contextual com contador "Selecionados X"        |
| RF-046.16 | Na aba "Ativos", a barra de ações deve exibir: "Editar", "Inativar", "Excluir", "Transferir para outra Agência"        |
| RF-046.17 | Na aba "Inativos", a barra de ações deve exibir: "Editar", "Ativar", "Excluir"                                         |
| RF-046.18 | O botão "Editar" deve estar habilitado apenas quando **1 agente** estiver selecionado                                  |
| RF-046.19 | Os botões "Inativar", "Ativar", "Excluir" e "Transferir" devem funcionar para múltiplos agentes selecionados           |

Paginação

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
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
| RF-046.30 | O modal deve exibir campo CPF (obrigatório, único no sistema, com validação de formato e dígito verificador)                                      |
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
| RF-046.38 | O Administrador deve poder selecionar um ou mais agentes ativos e acionar a ação "Transferir para outra Agência"                      |
| RF-046.39 | O sistema deve exibir modal para seleção da agência de destino                                                                        |
| RF-046.40 | O sistema deve exibir modal de confirmação com nome dos agentes e agência de destino antes de concluir a transferência                |
| RF-046.41 | Ao confirmar a transferência, o vínculo do agente deve ser atualizado para a nova agência                                             |
| RF-046.42 | O histórico de comissionamento gerado antes da transferência deve permanecer vinculado à agência de origem                            |
| RF-046.43 | O comissionamento gerado após a transferência deve ser vinculado à nova agência                                                       |

Colunas da Tabela

| Coluna            | Conteúdo                        | Ordenável | Observação                         |
|-------------------|---------------------------------|-----------|------------------------------------|
| Checkbox          | ☐                               | ❌         | Seleção múltipla                   |
| ID                | ID numérico                     | ✅         | Ordenação padrão DESC              |
| Nome              | Nome completo do agente         | ✅         | Ordena por nome                    |
| CPF               | `XXX.XXX.XXX-**` (mascarado)    | ❌         | Nunca exibido completo na listagem |
| E-mail            | E-mail de login                 | ✅         | —                                  |
| Agência Vinculada | Nome da agência                 | ✅         | Apenas na visão do Administrador   |
| Qtd Atrações      | Número inteiro                  | ✅         | Atrações autorizadas ao agente     |
| Status            | Badge Ativo / Inativo           | ✅         | —                                  |
| Data Cadastro     | DD/MM/AAAA                      | ✅         | —                                  |

Abas de Status

| Aba      | Descrição                           | Ações Disponíveis (Admin)                                 | Ações Disponíveis (Agência)          |
|----------|-------------------------------------|-----------------------------------------------------------|--------------------------------------|
| Ativos   | Agentes com status ativo            | Editar, Inativar, Excluir, Transferir para outra Agência  | Editar, Inativar, Desvincular        |
| Inativos | Agentes com status inativo          | Editar, Ativar, Excluir                                   | Editar, Ativar                       |
| Todos    | Todos os agentes (exceto excluídos) | Editar, Excluir, Inativar/Ativar                          | Editar, Inativar/Ativar, Desvincular |

Filtros Avançados (Botão Filtro)

| Filtro            | Tipo               | Opções / Formato          |
|-------------------|--------------------|---------------------------|
| Agência Vinculada | Multi-select       | Lista de agências ativas  |
| Status            | Select             | Ativo, Inativo            |
| Data de Cadastro  | Intervalo de datas | Data inicial - Data final |

Barra de Ações por Perfil

| Perfil         | Aba      | Ações                                                                              |
|----------------|----------|------------------------------------------------------------------------------------|
| Administrador  | Ativos   | [Selecionados X] [Editar] [Inativar] [Excluir] [Transferir para outra Agência]     |
| Administrador  | Inativos | [Selecionados X] [Editar] [Ativar] [Excluir]                                       |
| Agência        | Ativos   | [Selecionados X] [Editar] [Inativar] [Desvincular]                                 |
| Agência        | Inativos | [Selecionados X] [Editar] [Ativar]                                                 |

O botão "Editar" é habilitado apenas quando exatamente 1 agente está selecionado

Regras de Negócio

| ID        | Regra                                                                                                                                      |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| RN-046.01 | O perfil **Administrador** visualiza e gerencia todos os agentes do sistema, independentemente da agência                                  |
| RN-046.02 | O perfil **Agência** visualiza e gerencia apenas os agentes vinculados à sua própria agência                                               |
| RN-046.03 | Um agente deve estar vinculado a **apenas uma agência** por vez                                                                            |
| RN-046.04 | Agente com status **Inativo** não pode realizar vendas nem ser selecionado em transações                                                   |
| RN-046.05 | Ao desvincular um agente (ação do perfil Agência), o status do agente é automaticamente alterado para **Inativo** até novo vínculo         |
| RN-046.06 | O campo **e-mail é único** no sistema e utilizado como credencial de login do agente                                                       |
| RN-046.07 | O perfil **Agência** pode desvincular agentes, mas **não pode** excluí-los do sistema                                                      |
| RN-046.08 | Apenas o perfil **Administrador** pode transferir um agente de uma agência para outra                                                      |
| RN-046.09 | O histórico de comissões gerado antes de uma transferência **permanece vinculado à agência de origem**                                     |
| RN-046.10 | O **CPF deve ser mascarado** na listagem (`XXX.XXX.XXX-**`), sendo visível completo apenas no modal de edição/visualização                 |
| RN-046.11 | A busca por texto deve ser **case-insensitive** e operar sobre nome, CPF e e-mail                                                          |
| RN-046.12 | A paginação padrão exibe **10 registros** por página                                                                                       |
| RN-046.13 | A **senha do agente não deve** ser exibida em nenhuma tela após o cadastro                                                                 |

Critérios de Aceitação

| ID        | Critério                                                           | Resultado Esperado                                                                                   |
|-----------|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
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
| CA-046.13 | Transferir agente para outra agência (Admin)                       | Modal de seleção de agência exibido → modal de confirmação → vínculo atualizado + mensagem de sucesso |
| CA-046.14 | Desvincular agente (Agência)                                       | Agente removido da lista da agência + status alterado para Inativo + mensagem de sucesso             |
| CA-046.15 | Tentar cadastrar agente com e-mail já existente                    | Sistema exibe mensagem de erro "E-mail já cadastrado no sistema"                                     |
| CA-046.16 | Verificar agente inativo em fluxo de venda                         | Agente inativo não aparece disponível para seleção em nenhuma transação de venda                     |
| CA-046.17 | Alterar paginação para 50                                          | Lista atualiza exibindo até 50 registros por página                                                  |

Protótipo/Wireframe

Figura - WF-050 - Gestão de Agentes.png (a definir)
