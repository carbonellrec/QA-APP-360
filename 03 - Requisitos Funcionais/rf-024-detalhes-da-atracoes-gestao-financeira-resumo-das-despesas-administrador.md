### 3.24 Detalhes da Atrações/Gestão Financeira/Resumo das Despesas - Administrador

**ID:** RF-024

**Módulo** : Detalhes da Atração &gt; Gestão Financeira &gt; Resumo das Despesas

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador e Parceiro Comercial visualizar uma prévia das despesas e receitas por atração, agrupadas por data de liberação, e solicitar adiantamento de repasses.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                                                            |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.01 | O sistema deve exibir o título "Resumo das Despesas" no topo da página.                                                                                              |
| RF-024.02 | O sistema deve exibir o subtítulo "Condições comerciais do contrato" abaixo do título principal.                                                                     |
| RF-024.03 | O sistema deve exibir a tela no contexto do menu lateral: Detalhes da Atração > Gestão Financeira > Resumo das Despesas.                                             |
| RF-024.04 | O sistema deve exibir apenas as atrações vinculadas ao usuário logado (Administrador visualiza todas; Parceiro Comercial visualiza apenas suas atrações vinculadas). |

Tabela Principal - Resumo por Atração

| ID        | Requisito                                                                                                                                                                         |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.05 | O sistema deve exibir uma tabela principal agrupada por data de liberação contendo as seguintes colunas: Nome (da atração), Status, Data de Liberação, Receita Líquida e Repasse. |
| RF-024.06 | O sistema deve exibir na coluna "Nome" o nome da atração.                                                                                                                         |
| RF-024.07 | O sistema deve exibir na coluna "Status" um dos seguintes valores: "Aguardando Liberação" ou "Recebido".                                                                          |
| RF-024.08 | O sistema deve exibir na coluna "Data de Liberação" a data e hora da liberação no formato DD/MM/AAAA HH:MM:SS.                                                                    |
| RF-024.09 | O sistema deve exibir na coluna "Receita Líquida" o valor calculado da receita líquida da atração formatado como moeda brasileira (R$ X.XXX,XX).                                  |
| RF-024.10 | O sistema deve exibir na coluna "Repasse" um botão "Solicitar Repasse" para cada linha da tabela, quando aplicável.                                                               |
| RF-024.11 | O sistema deve permitir que o usuário clique na linha da tabela principal para expandir ou colapsar os detalhes da atração.                                                       |
| RF-024.12 | O sistema deve exibir visualmente quando uma linha está expandida (ex.: ícone de seta, cor de fundo diferenciada).                                                                |

Tabela Detalhada - Componentes Financeiros

| ID        | Requisito                                                                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.13 | O sistema deve exibir uma tabela detalhada abaixo de cada linha expandida da tabela principal contendo os componentes financeiros da atração.                                    |
| RF-024.14 | A tabela detalhada deve conter as seguintes colunas: Nome, Valor, Tipo, Status e Observações.                                                                                    |
| RF-024.15 | O sistema deve exibir na coluna "Nome" os tipos de componente financeiro, tais como: Ingressos, Comissão Agentes, Repasse, Encargos, e outros componentes conforme configurados. |
| RF-024.16 | O sistema deve exibir na coluna "Valor" o valor do componente formatado como moeda brasileira (R$ X.XXX,XX).                                                                     |
| RF-024.17 | O sistema deve exibir na coluna "Tipo" um dos seguintes valores: "Receita" ou "Despesas".                                                                                        |
| RF-024.18 | O sistema deve exibir na coluna "Status" um dos seguintes valores: "Recebido", "Pendente" ou "Bloqueio Financeiro".                                                              |
| RF-024.19 | O sistema deve exibir na coluna "Observações" as observações relacionadas ao componente, ou "" quando não houver observações.                                                    |
| RF-024.20 | O sistema deve calcular e exibir a "Receita Líquida" da tabela principal como a soma das receitas menos a soma das despesas dos componentes financeiros da atração.              |

Modal de Solicitação de Repasse

| ID        | Requisito                                                                                                                                                                                                                                                                                                           |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.21 | O sistema deve exibir um modal quando o usuário clicar no botão "Solicitar Repasse" da tabela principal.                                                                                                                                                                                                            |
| RF-024.22 | O sistema deve exibir no modal uma mensagem informando o valor disponível para repasse no formato "Você tem R$ X.XXX,XX liberados para repasse".                                                                                                                                                                    |
| RF-024.23 | O sistema deve calcular automaticamente o valor disponível para repasse baseado nas seguintes informações financeiras do contrato da atração: Percentual liberado para saque (ou Valor liberado para saque), Valor máximo para saque, Receita líquida disponível, Repasses já solicitados pendentes ou autorizados. |
| RF-024.24 | O sistema deve exibir um campo de entrada "Valor" no modal para que o usuário informe o valor que deseja solicitar como repasse.                                                                                                                                                                                    |
| RF-024.25 | O sistema deve exibir um botão "Valor Total" no modal que, ao ser clicado, preenche automaticamente o campo "Valor" com o valor máximo disponível para repasse.                                                                                                                                                     |
| RF-024.26 | O sistema deve exibir um botão de confirmação (ex.: "Confirmar" ou "Solicitar Repasse") no modal para confirmar a solicitação.                                                                                                                                                                                      |
| RF-024.27 | O sistema deve exibir um botão de cancelamento (ex.: "Cancelar" ou "Fechar") no modal para fechar o modal sem efetuar a solicitação.                                                                                                                                                                                |
| RF-024.28 | O sistema deve validar que o valor informado no campo "Valor" não seja maior que o valor disponível para repasse antes de confirmar a solicitação.                                                                                                                                                                  |
| RF-024.29 | O sistema deve validar que o valor informado no campo "Valor" não seja maior que o valor máximo permitido por solicitação antes de confirmar a solicitação.                                                                                                                                                         |
| RF-024.30 | O sistema deve criar uma nova despesa no registro da atração com o valor solicitado quando o usuário confirmar a solicitação de repasse.                                                                                                                                                                            |
| RF-024.31 | O sistema deve criar uma nova despesa no registro da atração com o valor da taxa de antecipação (obtida das Condições Comerciais do contrato) quando o usuário confirmar a solicitação de repasse.                                                                                                                  |
| RF-024.32 | O sistema deve definir o status inicial das despesas criadas (valor solicitado e taxa de antecipação) como "Pendente" após a solicitação de repasse.                                                                                                                                                                |
| RF-024.33 | O sistema deve atualizar a tabela detalhada automaticamente após a confirmação da solicitação de repasse, incluindo as novas despesas criadas.                                                                                                                                                                      |

Gestão de Status de Repasse

| ID        | Requisito                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.34 | O sistema deve permitir que usuários com perfil Administrador alterem o status das despesas de repasse de "Pendente" para "Autorizado".                               |
| RF-024.35 | O sistema deve permitir que usuários com perfil Administrador alterem o status das despesas de repasse de "Autorizado" para "Recebido" quando o repasse for efetuado. |
| RF-024.36 | O sistema deve atualizar automaticamente a tabela principal e detalhada quando houver alteração de status das despesas de repasse.                                    |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                                                                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-024.01 | O valor disponível para repasse deve ser calculado considerando: (Receita Líquida × Percentual liberado para saque) OU Valor liberado para saque (conforme configuração nas Informações Financeiras), limitado ao Valor máximo para saque, menos os repasses já solicitados com status "Pendente" ou "Autorizado".                                                   |
| RN-024.02 | O valor máximo permitido por solicitação de repasse é o Valor máximo para saque definido nas Informações Financeiras do contrato da atração.                                                                                                                                                                                                                         |
| RN-024.03 | O usuário não pode solicitar um novo repasse antes de aguardar o prazo de pagamento desde a última solicitação. O prazo é calculado a partir da data da última solicitação de repasse com status "Recebido" ou a partir da data de liberação, conforme o maior entre "Prazo pagamento" (Condições Comerciais) e "Tempo mínimo para saque" (Informações Financeiras). |
| RN-024.04 | O campo "Valor" no modal de solicitação de repasse é obrigatório e deve ser maior que zero.                                                                                                                                                                                                                                                                          |
| RN-024.05 | O valor informado no campo "Valor" não pode ser maior que o valor disponível para repasse exibido na mensagem do modal.                                                                                                                                                                                                                                              |
| RN-024.06 | O valor informado no campo "Valor" não pode ser maior que o valor máximo permitido por solicitação (Valor máximo para saque).                                                                                                                                                                                                                                        |
| RN-024.07 | A taxa de antecipação deve ser obtida do campo "Tx. Antecipação" das Condições Comerciais do contrato da atração.                                                                                                                                                                                                                                                    |
| RN-024.08 | Quando uma solicitação de repasse é confirmada, o sistema deve criar duas despesas: uma com o valor solicitado e outra com o valor da taxa de antecipação calculada sobre o valor solicitado.                                                                                                                                                                        |
| RN-024.09 | O status "Bloqueio Financeiro" deve ser exibido quando houver alguma restrição financeira que impeça o repasse, conforme definido nas observações do componente.                                                                                                                                                                                                     |
| RN-024.10 | Apenas usuários com perfil Administrador podem alterar o status das despesas de repasse de "Pendente" para "Autorizado" e de "Autorizado" para "Recebido".                                                                                                                                                                                                           |
| RN-024.11 | O agrupamento por data de liberação deve agrupar as atrações que possuem a mesma data de liberação. Quando todas as atrações têm a mesma data, não é necessário exibir cabeçalho de grupo visível.                                                                                                                                                                   |
| RN-024.12 | O Parceiro Comercial pode visualizar e solicitar repasse apenas para atrações vinculadas ao seu contrato.                                                                                                                                                                                                                                                            |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                                                                            | Resultado Esperado                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| CA-024.01 | Dado que um usuário Administrador acessa a tela Resumo das Despesas, quando visualizar a tabela principal, então o sistema deve exibir todas as atrações agrupadas por data de liberação com as colunas Nome, Status, Data de Liberação, Receita Líquida e Repasse. | Tabela principal exibe todas as atrações com as colunas especificadas. |
| CA-024.02 | Dado que um usuário Parceiro Comercial acessa a tela Resumo das Despesas, quando visualizar a tabela principal, então o sistema deve exibir apenas as atrações vinculadas ao seu contrato.                                                                          | Tabela principal exibe apenas atrações do Parceiro Comercial.          |
| CA-024.03 | Dado que o usuário clica em uma linha da tabela principal, quando a linha estiver colapsada, então o sistema deve expandir e exibir a tabela detalhada com os componentes financeiros da atração.                                                                   | Tabela detalhada é exibida abaixo da linha clicada.                    |
| CA-024.04 | Dado que o usuário clica no botão "Solicitar Repasse", quando o modal for exibido, então o sistema deve mostrar o valor disponível para repasse calculado corretamente baseado nas Informações Financeiras do contrato.                                             | Modal exibe valor disponível calculado corretamente.                   |
| CA-024.05 | Dado que o usuário clica no botão "Valor Total" no modal, quando o botão for acionado, então o sistema deve preencher o campo "Valor" com o valor máximo disponível para repasse.                                                                                   | Campo Valor é preenchido automaticamente com o valor máximo.           |
| CA-024.06 | Dado que o usuário informa um valor maior que o disponível no campo "Valor" do modal, quando tentar confirmar a solicitação, então o sistema deve exibir mensagem de erro e impedir a confirmação.                                                                  | Sistema valida e impede confirmação com valor inválido.                |
| CA-024.07 | Dado que o usuário confirma uma solicitação de repasse válida, quando a solicitação for processada, então o sistema deve criar duas despesas (valor solicitado e taxa de antecipação) com status "Pendente" e atualizar a tabela detalhada.                         | Duas despesas são criadas e tabela é atualizada.                       |
| CA-024.08 | Dado que um usuário Administrador altera o status de uma despesa de repasse de "Pendente" para "Autorizado", quando a alteração for confirmada, então o sistema deve atualizar o status na tabela detalhada.                                                        | Status é atualizado na tabela detalhada.                               |
| CA-024.09 | Dado que o usuário tenta solicitar um novo repasse antes de aguardar o prazo de pagamento, quando tentar acessar o modal, então o sistema deve impedir a solicitação ou exibir mensagem informando o prazo restante.                                                | Sistema valida prazo e impede ou informa prazo restante.               |
| CA-024.10 | Dado que uma atração possui receita líquida de R$ 100.000,00 e percentual liberado para saque de 50%, quando o sistema calcular o valor disponível, então deve exibir R$ 50.000,00 (ou o valor máximo para saque, se menor).                                        | Cálculo do valor disponível está correto.                              |

Ex.

| Dados                            | Valor         |
|----------------------------------|---------------|
| Percentual liberado para saque   | 50%           |
| Valor máximo liberado para saque | R$ 10.000,00  |
| Receita líquida                  | R$ 100.000,00 |
| Prazo para pagamento             | 15 dias       |

Protótipo/Wireframe

Figura  - WF-030 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Resumo das Despesas

### 3.25 Detalhes da Atrações/Tela de Validação de Ingressos
