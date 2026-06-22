### 3.17 Detalhes da Atrações/Gestão de Ingressos – Administrador.

**ID:** RF-017

**Módulo** : Detalhes da Atração &gt; Gestão de Ingressos

**Perfis** : Administrador, Parceiro Comercial, Editor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a gestão dos ingressos (lotes) vinculados a uma atração específica. Cada ingresso configura um lote de venda com categoria, valor, quantidade disponível e outras características. Um mesmo tipo de categoria pode ter múltiplos lotes com valores e quantidades diferentes.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------|
| RF-017.01 | O sistema deve exibir título "Gestão de Ingresso" com subtítulo "Gerencie os ingressos da atração" |
| RF-017.02 | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                   |
| RF-017.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                        |
| RF-017.04 | O sistema deve exibir botão "Adicionar Ingresso" que abre o modal de criação                       |

Sistema de Abas

| ID        | Requisito                                                               |
|-----------|-------------------------------------------------------------------------|
| RF-017.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
| RF-017.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
| RF-017.07 | A aba "Ativos" deve exibir ingressos com status "Ativo"                 |
| RF-017.08 | A aba "Inativos" deve exibir ingressos com status "Inativo"             |

Tabela de Ingressos

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-017.09 | O sistema deve exibir tabela com colunas: Checkbox, ID, Categorias, Status, Valor, Quantidade, Lote, Msg Customizada, Expiração do Pedido (h) |
| RF-017.10 | A coluna "Status" deve exibir badges: "Ativo" (azul) ou "Inativo" (cinza)                                                                     |
| RF-017.11 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                                                                           |
| RF-017.12 | A tabela deve ser ordenada por ID DESC por padrão                                                                                             |

Busca e Filtros

| ID        | Requisito                                                                 |
|-----------|---------------------------------------------------------------------------|
| RF-017.13 | O campo de pesquisa deve buscar por: ID, Categoria, Lote, Valor           |
| RF-017.14 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa |
| RF-017.15 | O botão Filtro deve abrir painel com filtros: Status, Categoria, Lote     |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-017.16 | O sistema deve permitir seleção múltipla via checkbox                                                       |
| RF-017.17 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Editar, Excluir, Inativar (toggle) |
| RF-017.18 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                            |

Ações Disponíveis

| ID        | Requisito                                                                    |
|-----------|------------------------------------------------------------------------------|
| RF-017.19 | Editar: Disponível apenas quando 1 item selecionado. Abre modal de edição    |
| RF-017.20 | Excluir: Exibe confirmação antes de executar. Permite exclusão em massa      |
| RF-017.21 | Inativar: Altera status para "Inativo". Permite inativação em massa          |
| RF-017.22 | Ativar (aba Inativos): Altera status para "Ativo". Permite ativação em massa |

Ação de Clique na Linha

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-017.23 | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-017.24 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-017.25 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-017.26 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Ingresso

| ID        | Requisito                                                                                                                               |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------|
| RF-017.27 | O modal deve exibir título dinâmico: "Novo Ingresso" (novo) ou "Editar Ingresso" (edição) ou "Visualizar Ingresso" (somente leitura)    |
| RF-017.28 | O modal deve exibir subtítulo: "Preencha os campos obrigatórios para adicionar um ingresso"                                             |
| RF-017.29 | O modal deve exibir botões: Descartar e Salvar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                              |
| RF-017.30 | Campo Categoria (obrigatório): Dropdown que lista categorias cadastradas na atração (RF-014). Permite busca por nome                    |
| RF-017.31 | Campo Valor (obrigatório): Campo numérico monetário com máscara R$ 0,00                                                                 |
| RF-017.32 | Campo Lote (obrigatório): Campo texto para número do lote (ex: 001, 002)                                                                |
| RF-017.33 | Campo Quantidade (obrigatório): Campo numérico para quantidade máxima de ingressos disponíveis para venda                               |
| RF-017.34 | Campo Expiração do pedido (h) (obrigatório): Campo numérico para tempo em horas que o cliente tem para pagar após adicionar ao carrinho |
| RF-017.35 | Campo Mensagem Customizada (opcional): Campo texto para mensagem que aparecerá no ingresso do cliente                                   |
| RF-017.36 | Campo Ativo (obrigatório): Toggle switch para ativar/desativar o ingresso. Padrão: Ativo                                                |

Regras de Negócio

| ID        | Regra                                                                                                                    |
|-----------|--------------------------------------------------------------------------------------------------------------------------|
| RN-017.01 | Cada ingresso possui apenas uma categoria vinculada                                                                      |
| RN-017.02 | Um mesmo tipo de categoria pode ter múltiplos lotes com valores e quantidades diferentes                                 |
| RN-017.03 | O número do lote deve ser único dentro da mesma atração                                                                  |
| RN-017.04 | Ingressos são sempre vinculados a uma atração específica (não são globais)                                               |
| RN-017.05 | O ID do ingresso é gerado automaticamente pelo sistema de forma incremental                                              |
| RN-017.06 | A mensagem customizada aparece no ingresso físico/digital do cliente após a compra                                       |
| RN-017.07 | A quantidade define o máximo de ingressos que podem ser vendidos para aquele lote                                        |
| RN-017.08 | Ao atingir a quantidade máxima vendida, o lote deve ser automaticamente inativado ou o sistema deve impedir novas vendas |
| RN-017.09 | Exclusão deve ser soft delete (marcação no banco de dados, não remoção física)                                           |
| RN-017.10 | Ingressos excluídos não aparecem em nenhuma aba e só podem ser recuperados pela equipe de TI                             |
| RN-017.11 | Ingressos inativos não aparecem como opção de compra para clientes                                                       |
| RN-017.12 | O sistema deve impedir a exclusão de ingressos que possuem vendas vinculadas                                             |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                     |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-017.01 | Dado que o usuário acessa Detalhes da Atração > Gestão de Ingressos, então deve visualizar a lista de ingressos na aba "Ativos"                                              |
| CA-017.02 | Dado que o usuário clica em "Adicionar Ingresso", quando preenche os campos obrigatórios e salva, então o ingresso deve aparecer na lista                                    |
| CA-017.03 | Dado que existe uma categoria "Estudante" com lote 001 (R$ 10,00), quando o usuário cria outro ingresso "Estudante" lote 002 (R$ 15,00), então ambos devem aparecer na lista |
| CA-017.04 | Dado que o usuário tenta criar ingresso com número de lote já existente na atração, então o sistema deve exibir erro de duplicidade                                          |
| CA-017.05 | Dado que o usuário seleciona múltiplos ingressos e clica em "Inativar", então todos devem ter seu status alterado para "Inativo"                                             |
| CA-017.06 | Dado que um lote atinge sua quantidade máxima vendida, então o sistema deve impedir novas vendas ou inativar automaticamente                                                 |
| CA-017.07 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de visualização com campos somente leitura                                                         |
| CA-017.08 | Dado que o usuário tenta excluir um ingresso com vendas vinculadas, então o sistema deve exibir erro e impedir a exclusão                                                    |

**Protótipo/Wireframe**

Figura  - WF-019 - Detalhes da Atração/Gestão de ingresso

Figura - WF-020 - Detalhes da Atração/Gestão de Ingresso/Adicionar Ingresso

### 3.18 Detalhes da Atrações/Gestão de Cupons – Administrador
