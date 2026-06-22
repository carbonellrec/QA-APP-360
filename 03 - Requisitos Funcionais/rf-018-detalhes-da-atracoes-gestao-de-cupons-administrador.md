### 3.18 Detalhes da Atrações/Gestão de Cupons – Administrador

**ID:** RF-018

**Módulo** : Detalhes da Atração &gt; Gestão de Cupons

**Perfis** : Administrador, Parceiro Comercial, Editor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a gestão de cupons de desconto vinculados a uma atração específica. Os cupons podem ser de dois tipos: Cupom Normal (disponível para todos os turistas) e Cupom Agência (vinculado a uma agência específica para controle de comissões). Cada cupom possui tipo de desconto (porcentagem ou valor fixo), quantidade máxima de usos, validade por período e dias da semana, categorias aplicáveis, e pode ser compartilhado via link único ou QR Code.

Requisitos Detalhados

Estrutura da Tela

| ID   | Requisito                                                                                          |
|------|----------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir título "Gestão de Cupons" com subtítulo "Gerencie os cupons da atração"      |
|      | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                   |
|      | O sistema deve exibir botão "Filtro" para filtros avançados                                        |
|      | O sistema deve exibir botão "Adicionar Cupom" que abre o modal de criação de cupom normal          |
|      | O sistema deve exibir botão "Adicionar Cupom Agencia" que abre o modal de criação de cupom agência |

Sistema de Abas

| ID   | Requisito                                                               |
|------|-------------------------------------------------------------------------|
|      | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
|      | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
|      | A aba "Ativos" deve exibir cupons com status "Ativo"                    |
|      | A aba "Inativos" deve exibir cupons com status "Inativo" ou "Expirado"  |

Tabela de Cupons

| ID   | Requisito                                                                                                                                                                                                  |
|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir tabela com colunas: Checkbox, ID, Nome, Usuário Relacionado, Status, Porcentagem/valor, Valor, Quantidade, Link, Saldo, Mostrar na Atração, Dias da semana, Início, Final, Categoria |
|      | A coluna "Status" deve exibir badges: "Ativo" (azul), "Inativo" (cinza) ou "Expirado" (vermelho)                                                                                                           |
|      | A coluna "Porcentagem/valor" deve exibir "Porcentagem" ou "Valor" conforme o tipo de desconto                                                                                                              |
|      | A coluna "Valor" deve exibir "% 10%" quando tipo for Porcentagem ou "R$ 10,00" quando tipo for Valor                                                                                                       |
|      | A coluna "Link" deve exibir o link caso já tenha sido gerado e um botão para copiar o link.                                                                                                                |
|      | A coluna "Saldo" deve exibir a quantidade restante (Quantidade - Utilizados) e atualizar automaticamente quando o cupom é usado                                                                            |

Busca e Filtros

| ID   | Requisito                                                                                                       |
|------|-----------------------------------------------------------------------------------------------------------------|
|      | O campo de pesquisa deve buscar por: ID, Nome, Categoria                                                        |
|      | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                                       |
|      | O botão Filtro deve abrir painel com filtros: Status, Tipo (Normal/Agência), Categoria, Data Início, Data Final |

Seleção e Ações em Massa

| ID   | Requisito                                                                                                                           |
|------|-------------------------------------------------------------------------------------------------------------------------------------|
|      | O sistema deve permitir seleção múltipla via checkbox                                                                               |
|      | Ao selecionar mais itens, exibir barra de ações: "Selecionados X", Gerar link, Excluir, Inativar (toggle)                           |
|      | Ao selecionar apenas um item, exibir barra de ações: "Selecionados X", Gerar link, Compartilhar, Editar, Excluir, Inativar (toggle) |
|      | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                                                    |
|      | A ação "Gerar link" deve estar disponível para múltiplos cupons selecionados                                                        |
|      | A ação "Compartilhar" deve estar disponível para múltiplos cupons selecionados                                                      |

Ações Disponíveis

| ID   | Requisito                                                                                                         |
|------|-------------------------------------------------------------------------------------------------------------------|
|      | Gerar link: Cria link único para o cupom (ex: curitiba360.com/joao10). Abre modal de QR Code com o link e QR Code |
|      | Compartilhar: Gera o link (se não existir) e abre WhatsApp para compartilhar o link do cupom                      |
|      | Editar: Disponível apenas quando 1 item selecionado. Abre modal de edição                                         |
|      | Excluir: Exibe confirmação antes de executar. Permite exclusão em massa                                           |
|      | Inativar: Altera status para "Inativo". Permite inativação em massa                                               |
|      | Ativar (aba Inativos): Altera status para "Ativo". Permite ativação em massa                                      |

Ação de Clique na Linha

| ID   | Requisito                                                                                       |
|------|-------------------------------------------------------------------------------------------------|
|      | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID   | Requisito                                                                                                |
|------|----------------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir 10 registros por padrão                                                            |
|      | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
|      | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Cupom (Normal)

| ID   | Requisito                                                                                                                                                    |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O modal deve exibir título dinâmico: "Novo Cupom" (novo) ou "Editar Cupom" (edição) ou "Visualizar Cupom" (somente leitura)                                  |
|      | O modal deve exibir subtítulo: "Preencha os campos obrigatórios para adicionar um cupom"                                                                     |
|      | O modal deve exibir botões: Descartar e Salvar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                                                   |
|      | Campo Usuário Relacionado (obrigatório): Campo de seleção única e pesquisável com o nome do usuário que irá receber a comissão                               |
|      | Campo Nome (obrigatório): Campo texto para nome do cupom (ex: JOAO10)                                                                                        |
|      | Campo Porcentagem/Valor (obrigatório): Dropdown com opções "Porcentagem" ou "Valor"                                                                          |
|      | Campo Valor (obrigatório): Campo numérico. Se Porcentagem: exibir "% 10%". Se Valor: exibir "R$ 10,00"                                                       |
|      | Campo Quantidade (obrigatório): Campo numérico para quantidade máxima de ingressos com desconto                                                              |
|      | Campo Mostrar na atração (obrigatório): Radio buttons "Sim" ou "Não". Quando "Sim", cupom aparece na página principal da atração                             |
|      | Campo Início (obrigatório): Date/time picker para início da validade do cupom                                                                                |
|      | Campo Fim (obrigatório): Date/time picker para fim da validade do cupom                                                                                      |
|      | Campo Categorias (obrigatório): Multiseleção com checkboxes das categorias cadastradas na atração (RF-014). Cupom válido para qualquer categoria selecionada |
|      | Campo Ativo (obrigatório): Toggle switch para ativar/desativar o cupom. Padrão: Ativo                                                                        |

Modal Adicionar/Editar Cupom Agência

| ID   | Requisito                                                                                                                                                                                     |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O modal deve conter todos os campos do Cupom Normal (RF-018.33 a RF-018.45) mais o campo Agência (obrigatório): Dropdown que lista todas as agências cadastradas, permite digitar para buscar |

Modal QR Code

| ID   | Requisito                                                                                   |
|------|---------------------------------------------------------------------------------------------|
|      | O modal deve exibir título "QR Code"                                                        |
|      | O modal deve exibir instrução: "Escaneie o QR Code ou copie o link"                         |
|      | O modal deve exibir QR Code gerado para o link do cupom                                     |
|      | O modal deve exibir campo com o link do cupom (ex: curitiba360.com/joao10) e botão "Copiar" |

Regras de Negócio

| ID        | Regra                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-018.01 | Cupons são sempre vinculados a uma atração específica (não são globais)                                                                          |
| RN-018.02 | O ID do cupom é gerado automaticamente pelo sistema de forma incremental                                                                         |
| RN-018.03 | O nome do cupom deve ser único dentro da mesma atração                                                                                           |
| RN-018.04 | Cupom Normal é disponível para todos os turistas e visitantes da plataforma                                                                      |
| RN-018.05 | Cupom Agência é vinculado a uma agência específica para controle de comissões. A agência divulga o cupom, mas pode ser usado por qualquer pessoa |
| RN-018.06 | O saldo do cupom (Quantidade - Utilizados) deve ser atualizado automaticamente quando o cupom é usado em uma compra                              |
| RN-018.07 | O link do cupom é gerado automaticamente quando o usuário clica em "Gerar link" ou "Compartilhar"                                                |
| RN-018.08 | O link do cupom é único e pode ser compartilhado e usado por qualquer pessoa                                                                     |
| RN-018.09 | O link permite múltiplos usos até atingir a quantidade máxima                                                                                    |
| RN-018.10 | Quando "Mostrar na Atração" está como "Sim", o cupom aparece no checkout da atração                                                              |
| RN-018.11 | Quando múltiplas categorias são selecionadas, o cupom é válido para qualquer uma delas                                                           |
| RN-018.12 | O cupom pode ser usado apenas nos dias da semana selecionados                                                                                    |
| RN-018.13 | A data "Início" deve ser anterior à data "Final". O sistema deve validar e impedir salvar se inválido                                            |
| RN-018.14 | Cupons com data final passada devem ser automaticamente inativados e marcados com status "Expirado"                                              |
| RN-018.15 | Quando a quantidade máxima é atingida, o cupom deve ser automaticamente inativado                                                                |
| RN-018.16 | Exclusão deve ser soft delete (marcação no banco de dados, não remoção física)                                                                   |
| RN-018.17 | Cupons excluídos não aparecem em nenhuma aba e só podem ser recuperados pela equipe de TI                                                        |
| RN-018.18 | Cupons inativos ou expirados não aparecem como opção de uso para clientes                                                                        |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                      |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-018.01 | Dado que o usuário acessa Detalhes da Atração > Gestão de Cupons, então deve visualizar a lista de cupons na aba "Ativos"                                                     |
| CA-018.02 | Dado que o usuário clica em "Adicionar Cupom", quando preenche os campos obrigatórios e salva, então o cupom deve aparecer na lista                                           |
| CA-018.03 | Dado que o usuário cria um Cupom Agência vinculado à "Agência Silva", quando um turista usa esse cupom, então o uso deve ficar vinculado à agência para controle de comissões |
| CA-018.04 | Dado que o usuário seleciona um cupom e clica em "Gerar link", então deve abrir o modal de QR Code com o link e QR Code gerados                                               |
| CA-018.05 | Dado que o usuário seleciona um cupom e clica em "Compartilhar", quando o link não existe, então o sistema deve gerar o link e abrir WhatsApp para compartilhamento           |
| CA-018.06 | Dado que um cupom tem quantidade máxima de 50 e já foi usado 10 vezes, então o saldo deve exibir 40                                                                           |
| CA-018.07 | Dado que um cupom atinge sua quantidade máxima de usos, então o sistema deve inativar automaticamente o cupom                                                                 |
| CA-018.08 | Dado que a data final de um cupom passa, então o sistema deve inativar automaticamente e marcar como "Expirado"                                                               |
| CA-018.09 | Dado que o usuário tenta salvar um cupom com data "Início" posterior à data "Final", então o sistema deve exibir erro e impedir o salvamento                                  |
| CA-018.10 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de visualização com campos somente leitura                                                          |

**Protótipo/Wireframe**

Figura  - WF-021 - Detalhes da Atração/Gestão de Cupons

Figura  - WF-022 - Detalhes da Atração/Gestão de Cupons/Gerar QR Code

Figura  - WF-023 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom

Figura  - WF-024 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom Agencia

### 3.19 Detalhes da Atrações/Gráficos Analytics - Administrador
