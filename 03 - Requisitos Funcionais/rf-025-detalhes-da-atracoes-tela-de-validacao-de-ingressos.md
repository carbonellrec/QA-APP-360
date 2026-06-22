### 3.25 Detalhes da Atrações/Tela de Validação de Ingressos

**ID:** RF-025

**Módulo** : Detalhes da Atração &gt; Validação de Ingressos

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas), Leitor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador, Parceiro Comercial e Leitor validar ingressos de turistas através da leitura de QR Code utilizando a câmera do dispositivo.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-025.01 | O sistema deve exibir o título "Validar Ingressos" no topo da página.                                       |
| RF-025.02 | O sistema deve exibir o subtítulo "Histórico de ingressos validados" abaixo do título principal.            |
| RF-025.03 | O sistema deve exibir a tela no contexto do menu lateral: Detalhes da Atração > Validar Ingressos.          |
| RF-025.04 | O sistema deve exibir o contexto da atração (nome e localização) no topo da barra lateral quando aplicável. |
| RF-025.05 | O sistema deve exibir apenas os ingressos da atração selecionada no contexto de Detalhes da Atração.        |
| RF-025.06 | O Parceiro Comercial deve visualizar apenas ingressos das atrações vinculadas ao seu contrato.              |
| RF-025.07 | O Leitor deve visualizar apenas ingressos das atrações às quais está vinculado.                             |

Barra de Ferramentas

| ID        | Requisito                                                                                                                                             |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.08 | O sistema deve exibir um campo de busca no topo da tela para pesquisar ingressos por ID, nome do titular ou e-mail.                                   |
| RF-025.09 | O sistema deve exibir um botão "Filtro" com ícone de funil no topo da tela para aplicar filtros aos ingressos exibidos.                               |
| RF-025.10 | O sistema deve exibir um botão "Iniciar Validação" com ícone de câmera no topo da tela para iniciar o processo de validação de um novo ingresso.      |
| RF-025.11 | O sistema deve permitir que o usuário digite termos de busca no campo de pesquisa e atualize a lista de ingressos em tempo real conforme a digitação. |

Abas de Status

| ID        | Requisito                                                                                                                 |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RF-025.12 | O sistema deve exibir três abas abaixo da barra de ferramentas: "Todos", "Validados" e "Cancelados".                      |
| RF-025.13 | O sistema deve exibir a aba "Todos" como ativa por padrão ao carregar a tela.                                             |
| RF-025.14 | O sistema deve permitir que o usuário clique em uma aba para filtrar os ingressos exibidos conforme o status selecionado. |
| RF-025.15 | O sistema deve exibir visualmente qual aba está ativa (ex.: sublinhado, cor diferenciada).                                |
| RF-025.16 | A aba "Todos" deve exibir todos os ingressos independente do status.                                                      |
| RF-025.17 | A aba "Validados" deve exibir apenas ingressos com status "Validado".                                                     |
| RF-025.18 | A aba "Cancelados" deve exibir apenas ingressos com status "Cancelado" ou "Erro de leitura".                              |

Tabela de Histórico de Ingressos

| ID        | Requisito                                                                                                                                                              |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.19 | O sistema deve exibir uma tabela com o histórico de ingressos validados contendo as seguintes colunas: ID Ingresso, Nome, Status, Data/hora da Leitura e Validado por. |
| RF-025.20 | O sistema deve exibir na coluna "ID Ingresso" o número de identificação único do ingresso.                                                                             |
| RF-025.21 | O sistema deve exibir um ícone de documento ao lado do ID do ingresso indicando que é possível copiar o ID.                                                            |
| RF-025.22 | O sistema deve permitir que o usuário clique no ícone de documento ou no ID do ingresso para copiar o ID para a área de transferência.                                 |
| RF-025.23 | O sistema deve exibir feedback visual quando o ID for copiado com sucesso (ex.: mensagem temporária "ID copiado").                                                     |
| RF-025.24 | O sistema deve exibir na coluna "Nome" o nome completo do titular do ingresso na primeira linha e o e-mail do titular na segunda linha (formato de duas linhas).       |
| RF-025.25 | O sistema deve exibir na coluna "Status" um badge/botão visual com o status da validação.                                                                              |
| RF-025.26 | O sistema deve exibir o status "Validado" em um badge de cor azul escuro quando o ingresso foi validado com sucesso.                                                   |
| RF-025.27 | O sistema deve exibir o status "Erro de leitura" em um badge de cor cinza claro quando houve erro na leitura do QR Code.                                               |
| RF-025.28 | O sistema deve exibir o status "Cancelado" em um badge de cor cinza claro quando o ingresso foi cancelado.                                                             |
| RF-025.29 | O sistema deve exibir na coluna "Data/hora da Leitura" a data e hora em que o ingresso foi lido/validado no formato DD/MM/AAAA HH:MM:SS.                               |
| RF-025.30 | O sistema deve exibir na coluna "Validado por" o nome do usuário (Leitor, Administrador ou Parceiro Comercial) que realizou a validação do ingresso.                   |
| RF-025.31 | O sistema deve permitir ordenação ascendente ou descendente em todas as colunas da tabela através de setas de ordenação.                                               |

Paginação

| ID        | Requisito                                                                                                                                                                                               |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.33 | O sistema deve exibir controles de paginação na parte inferior da tabela quando houver mais ingressos do que o limite de itens por página.                                                              |
| RF-025.34 | O sistema deve exibir um seletor (dropdown) para escolher o número de itens exibidos por página (ex.: 10, 25, 50, 100).                                                                                 |
| RF-025.35 | O sistema deve exibir botões de navegação: primeira página ("<<"), página anterior ("<"), próxima página (">") e última página (">>").                                                                  |
| RF-025.36 | O sistema deve exibir informações sobre a paginação no formato "X a Y de Z" (ex.: "1 a 10 de 200"), onde X é o primeiro item da página atual, Y é o último item da página atual e Z é o total de itens. |
| RF-025.37 | O sistema deve atualizar a tabela automaticamente quando o usuário alterar o número de itens por página ou navegar entre páginas.                                                                       |

Processo de Validação de Ingressos

| ID        | Requisito                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.38 | O sistema deve exibir um modal ou tela de validação quando o usuário clicar no botão "Iniciar Validação".                                                             |
| RF-025.39 | O sistema deve solicitar permissão de acesso à câmera do dispositivo quando o usuário iniciar a validação.                                                            |
| RF-025.40 | O sistema deve exibir mensagem informativa se o usuário negar permissão de acesso à câmera, explicando que a câmera é necessária para validar ingressos.              |
| RF-025.41 | O sistema deve exibir a visualização da câmera em tempo real quando a permissão for concedida.                                                                        |
| RF-025.42 | O sistema deve processar automaticamente o QR Code quando ele for detectado na visualização da câmera.                                                                |
| RF-025.43 | O sistema deve validar se o QR Code lido corresponde a um ingresso válido da atração atual.                                                                           |
| RF-025.44 | O sistema deve verificar se o ingresso não foi cancelado antes de permitir a validação.                                                                               |
| RF-025.45 | O sistema deve verificar se o ingresso não foi já validado anteriormente antes de permitir uma nova validação.                                                        |
| RF-025.46 | O sistema deve exibir feedback visual imediato após a leitura do QR Code indicando sucesso ou erro na validação.                                                      |
| RF-025.47 | O sistema deve exibir mensagem de sucesso quando o ingresso for validado com sucesso (ex.: "Ingresso validado com sucesso!").                                         |
| RF-025.48 | O sistema deve exibir mensagem de erro quando o ingresso estiver cancelado (ex.: "Ingresso cancelado. Entrada bloqueada.").                                           |
| RF-025.49 | O sistema deve exibir mensagem de erro quando houver erro na leitura do QR Code (ex.: "Erro na leitura do QR Code. Tente novamente.").                                |
| RF-025.50 | O sistema deve exibir mensagem de erro quando o ingresso já foi validado anteriormente (ex.: "Ingresso já foi validado anteriormente.").                              |
| RF-025.51 | O sistema deve registrar no histórico a validação realizada, incluindo: ID do ingresso, data/hora da leitura, status da validação e usuário que realizou a validação. |
| RF-025.52 | O sistema deve atualizar automaticamente a tabela de histórico após uma validação bem-sucedida ou com erro.                                                           |
| RF-025.53 | O sistema deve permitir que o usuário feche o modal/tela de validação e retorne à lista de histórico.                                                                 |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-025.01 | Ao clicar no botão "Iniciar Validação", o sistema deve solicitar permissão de acesso à câmera do dispositivo. Se a permissão for negada, o sistema deve exibir mensagem informativa e não permitir a validação até que a permissão seja concedida. |
| RN-025.02 | O sistema deve bloquear a entrada (não permitir validação) quando o ingresso estiver com status "Cancelado".                                                                                                                                       |
| RN-025.03 | O sistema deve bloquear a entrada (não permitir validação) quando houver erro na leitura do QR Code (QR Code inválido, corrompido ou não reconhecido).                                                                                             |
| RN-025.04 | O sistema deve permitir apenas uma validação por ingresso. Se um ingresso já foi validado anteriormente, o sistema deve exibir mensagem informando que o ingresso já foi validado e não permitir nova validação.                                   |
| RN-025.05 | O QR Code lido deve corresponder a um ingresso válido da atração atual. Se o QR Code pertencer a outra atração, o sistema deve exibir mensagem de erro.                                                                                            |
| RN-025.06 | A busca deve ser realizada em tempo real, filtrando os resultados conforme o usuário digita no campo de pesquisa. A busca deve considerar ID do ingresso, nome do titular e e-mail.                                                                |
| RN-025.07 | Os filtros devem permitir filtrar por: data/hora da leitura (período), status (Validado, Cancelado, Erro de leitura), validado por (nome do usuário), e outros critérios conforme necessário.                                                      |
| RN-025.08 | A ordenação das colunas deve ser persistente durante a sessão do usuário, mas não deve ser salva entre sessões diferentes.                                                                                                                         |
| RN-025.09 | O número padrão de itens por página deve ser 10, mas o usuário pode alterar para 25, 50 ou 100 itens por página.                                                                                                                                   |
| RN-025.10 | O Administrador pode visualizar e validar ingressos de todas as atrações do sistema.                                                                                                                                                               |
| RN-025.11 | O Parceiro Comercial pode visualizar e validar ingressos apenas das atrações vinculadas ao seu contrato.                                                                                                                                           |
| RN-025.12 | O Leitor pode visualizar e validar ingressos apenas das atrações às quais está vinculado através do cadastro de usuários da atração (RF-021).                                                                                                      |
| RN-025.13 | A data/hora da leitura deve ser registrada no momento exato em que o QR Code é lido com sucesso, utilizando o horário do servidor.                                                                                                                 |
| RN-025.14 | O campo "Validado por" deve registrar o nome completo do usuário logado que realizou a validação, não apenas o perfil.                                                                                                                             |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                                                                         | Resultado Esperado                                                                |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| CA-025.01 | Dado que um usuário Administrador acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir o histórico de todos os ingressos validados da atração com as colunas ID Ingresso, Nome, Status, Data/hora da Leitura e Validado por. | Tabela exibe todos os ingressos da atração com as colunas especificadas.          |
| CA-025.02 | Dado que um usuário Parceiro Comercial acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir apenas ingressos das atrações vinculadas ao seu contrato.                                                                        | Tabela exibe apenas ingressos do Parceiro Comercial.                              |
| CA-025.03 | Dado que um usuário Leitor acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir apenas ingressos das atrações às quais está vinculado.                                                                                       | Tabela exibe apenas ingressos das atrações vinculadas ao Leitor.                  |
| CA-025.04 | Dado que o usuário clica no botão "Iniciar Validação", quando a permissão de câmera for solicitada e concedida, então o sistema deve exibir a visualização da câmera em tempo real.                                                                              | Visualização da câmera é exibida em tempo real.                                   |
| CA-025.05 | Dado que o usuário escaneia um QR Code válido de um ingresso não cancelado e não validado anteriormente, quando o QR Code for lido, então o sistema deve validar o ingresso com sucesso, registrar no histórico e atualizar a tabela automaticamente.            | Ingresso é validado, registrado no histórico e tabela é atualizada.               |
| CA-025.06 | Dado que o usuário escaneia um QR Code de um ingresso cancelado, quando o QR Code for lido, então o sistema deve bloquear a entrada, exibir mensagem "Ingresso cancelado. Entrada bloqueada." e registrar no histórico com status "Cancelado".                   | Entrada é bloqueada, mensagem é exibida e registro é criado com status Cancelado. |
| CA-025.07 | Dado que o usuário escaneia um QR Code inválido ou corrompido, quando o QR Code for lido, então o sistema deve exibir mensagem "Erro na leitura do QR Code. Tente novamente." e registrar no histórico com status "Erro de leitura".                             | Mensagem de erro é exibida e registro é criado com status Erro de leitura.        |
| CA-025.08 | Dado que o usuário tenta validar um ingresso já validado anteriormente, quando o QR Code for lido, então o sistema deve exibir mensagem "Ingresso já foi validado anteriormente." e não permitir nova validação.                                                 | Mensagem é exibida e nova validação é bloqueada.                                  |
| CA-025.09 | Dado que o usuário clica no ícone de documento ao lado do ID do ingresso, quando o clique for realizado, então o sistema deve copiar o ID para a área de transferência e exibir feedback visual "ID copiado".                                                    | ID é copiado e feedback visual é exibido.                                         |
| CA-025.10 | Dado que o usuário digita um termo no campo de busca, quando o termo for digitado, então o sistema deve filtrar a lista de ingressos em tempo real, exibindo apenas os ingressos que correspondem ao termo pesquisado (ID, nome ou e-mail).                      | Lista é filtrada em tempo real conforme a digitação.                              |
| CA-025.11 | Dado que o usuário clica na aba "Validados", quando a aba for selecionada, então o sistema deve exibir apenas ingressos com status "Validado" na tabela.                                                                                                         | Tabela exibe apenas ingressos validados.                                          |
| CA-025.12 | Dado que o usuário clica em uma coluna da tabela para ordenar, quando a ordenação for aplicada, então o sistema deve reorganizar os ingressos conforme a ordenação selecionada (ascendente ou descendente) e exibir visualmente a coluna ordenada.               | Ingressos são reorganizados e coluna ordenada é destacada visualmente.            |

Protótipo/Wireframe

Figura  - WF-031 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Validar Ingressos
