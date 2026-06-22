### 3.16 Detalhes da Atrações/Pesquisar Ingresso/Detalhes – Administrador

**ID:** RF-016

**Módulo** : Detalhes da Atração &gt; Pesquisar Ingresso &gt; Detalhes

**Perfis** : Administrador, Parceiro Comercial, Editor, Leitor

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve exibir um modal com informações detalhadas do ingresso selecionado, incluindo dados do pedido, dados do cliente e dados específicos do ingresso. O modal é somente visualização, sem opções de edição ou ações.

Requisitos Detalhados

Estrutura do Modal

| ID        | Requisito                                                                   |
|-----------|-----------------------------------------------------------------------------|
| RF-016.01 | O modal deve exibir título dinâmico: "Detalhes do ingresso código [CÓDIGO]" |
| RF-016.02 | O modal deve exibir botão de fechar (X) no canto superior direito           |
| RF-016.03 | O modal é somente visualização (não permite edição de nenhum campo)         |
| RF-016.04 | O modal NÃO possui botões de ação (Validar, Cancelar, etc.)                 |

Seção: Pedido

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-016.05 | O sistema deve exibir seção "Pedido" com os dados do pedido original                             |
| RF-016.06 | Campos da seção Pedido: Código, Status, Forma de Pagamento, Vendedor, Data Hora Pedido, Obs      |
| RF-016.07 | O campo "Status do Pedido" deve exibir: Reservado, Finalizado, Cancelado ou Expirado             |
| RF-016.08 | O campo "Vendedor" deve exibir quem intermediou a venda (Agente/Agência ou indicar venda direta) |
| RF-016.09 | O campo "Obs" exibe a mensagem customizada definida na criação do ingresso (RF-017)              |

Status do Pedido

| ID        | Requisito                                                                 |
|-----------|---------------------------------------------------------------------------|
| RF-016.10 | Reservado: Pedido criado, aguardando pagamento                            |
| RF-016.11 | Finalizado: Pedido pago e ingressos emitidos                              |
| RF-016.12 | Cancelado: Pedido cancelado pelo operadora de pagamentos ou administrador |
| RF-016.13 | Expirado: Pedido não pago dentro do prazo de expiração                    |

Seção: Dados do Cliente

| ID        | Requisito                                                                   |
|-----------|-----------------------------------------------------------------------------|
| RF-016.14 | O sistema deve exibir seção "Dados do cliente" com informações do comprador |
| RF-016.15 | Campos da seção: Nome, Email, CPF/CNPJ, Telefone, Celular                   |
| RF-016.16 | Os dados do cliente são os informados no momento da compra                  |

Seção: Dados do Ingresso

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-016.17 | O sistema deve exibir seção "Dados do Ingresso" com informações específicas do ingresso                  |
| RF-016.18 | Campos da seção (linha 1): Código, Atração, Categoria, Localização, PDV                                  |
| RF-016.19 | Campos da seção (linha 2): Status, Data Criação, Data Impressão, Valor, Taxa Administrativa, Valor Total |
| RF-016.20 | O campo "Categoria" exibe o tipo de ingresso (ex: Morador de Curitiba Adulto, Estudante, Idoso)          |
| RF-016.21 | O campo "Localização" exibe o nome personalizado do local de acesso do ingresso                          |
| RF-016.22 | O campo "PDV" (Ponto de Venda) exibe: "Site" ou "App"                                                    |
| RF-016.23 | O campo "Valor Total" = Valor + Taxa Administrativa                                                      |

Regras de Negócio

| ID        | Regra                                                                                                                  |
|-----------|------------------------------------------------------------------------------------------------------------------------|
| RN-016.01 | Um pedido pode ter múltiplos ingressos. O modal exibe os dados de apenas um ingresso por vez                           |
| RN-016.02 | O campo "Vendedor" exibe o nome do Agente/Agência que intermediou a venda, ou o nome da plataforma para vendas diretas |
| RN-016.03 | A "Data Impressão" é preenchida quando o cliente visualiza/baixa o ingresso pela primeira vez                          |
| RN-016.04 | Se o ingresso nunca foi impresso/visualizado, o campo "Data Impressão" fica vazio                                      |
| RN-016.05 | O campo "Obs" é somente leitura e vem preenchido automaticamente conforme configuração da categoria                    |

Critérios de Aceitação

| ID        | Critério                                                                                                                                   |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| CA-016.01 | Dado que o usuário clica em uma linha na tela de Pesquisar Ingresso, então deve abrir o modal com os detalhes do ingresso selecionado      |
| CA-016.02 | Dado que o modal está aberto, então todos os campos devem estar em modo somente leitura                                                    |
| CA-016.03 | Dado que o usuário clica no botão X, então o modal deve fechar e retornar à lista de ingressos                                             |
| CA-016.04 | Dado que o ingresso pertence a um pedido com múltiplos ingressos, então o modal deve exibir apenas os dados do ingresso específico clicado |
| CA-016.05 | Dado que a venda foi intermediada por um agente, então o campo "Vendedor" deve exibir o nome do agente                                     |

**Protótipo/Wireframe**

Figura  - WF-018 - Detalhes da Atração/Pesquisar Ingresso/Detalhe do Ingresso

### 3.17 Detalhes da Atrações/Gestão de Ingressos – Administrador.
