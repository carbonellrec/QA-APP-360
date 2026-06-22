### 3.56 Tela Inicial por Perfil — Backoffice (Parceiro Comercial, Editor, Leitor, Agência, Agente)

**ID:** RF-056

Módulo: Backoffice > Tela Inicial

Perfis com Acesso: Parceiro Comercial, Editor, Leitor, Agência, Agente

**Prioridade:** Alta (Essencial)

**Descrição:** Este requisito complementa RF-002 (Tela Inicial — Backoffice), que define o menu lateral e o comportamento da interface para o perfil Administrador. Conforme previsto em RN-002.03, os demais perfis do Backoffice — Parceiro Comercial, Editor, Leitor, Agência e Agente — têm suas telas iniciais, menus disponíveis e regras de navegação definidos neste documento. Cada perfil é direcionado automaticamente, após o login, para a tela de aterrissagem correspondente à sua função, visualizando apenas os módulos aos quais tem acesso, sem possibilidade de navegar para áreas restritas.

Requisitos Detalhados

Elementos Comuns da Interface

| ID        | Requisito |
|-----------|-----------|
| RF-056.01 | O sistema deve exibir o nome completo do usuário logado no cabeçalho da interface para todos os perfis |
| RF-056.02 | O sistema deve exibir a foto de perfil do usuário ou um avatar padrão no cabeçalho, conforme configurado em RF-005 |
| RF-056.03 | O sistema deve exibir o botão "Sair" no cabeçalho para todos os perfis |
| RF-056.04 | Ao clicar em "Sair", o sistema deve exibir pop-up de confirmação com as opções "Confirmar" e "Cancelar" antes de encerrar a sessão |
| RF-056.05 | O sistema deve exibir um menu lateral contendo exclusivamente os módulos disponíveis para o perfil logado |
| RF-056.06 | O menu lateral deve permitir ser recolhido (collapsed) e expandido (expanded) via ícone de alternância |
| RF-056.07 | Quando recolhido, o menu lateral deve exibir apenas os ícones dos módulos, com tooltip ao passar o cursor |
| RF-056.08 | O item de menu correspondente à tela atualmente exibida deve ser destacado visualmente (estado ativo) |
| RF-056.09 | O sistema deve exibir o nome do perfil do usuário logado (ex.: "Parceiro Comercial", "Editor") abaixo do nome no cabeçalho |
| RF-056.10 | O sistema deve redirecionar automaticamente o usuário para a tela inicial correspondente ao seu perfil imediatamente após o login bem-sucedido |

Parceiro Comercial

| ID        | Requisito |
|-----------|-----------|
| RF-056.11 | Após o login, o sistema deve direcionar o Parceiro Comercial para a tela Totais da Atração (RF-004) da primeira atração vinculada ao seu perfil |
| RF-056.12 | O menu lateral do Parceiro Comercial deve conter os seguintes módulos: Totais da Atração, Pesquisar Ingresso, Gestão de Ingressos, Gestão de Cupons, Gráficos e Analytics, Editar Atração, Usuários da Atração, Relatórios da Atração, Negociação Financeira, Resumo de Despesas, Perfil |
| RF-056.13 | Quando o Parceiro Comercial estiver vinculado a mais de uma atração, o sistema deve exibir um seletor de atração no topo da interface (acima do conteúdo principal), permitindo alternar entre as atrações vinculadas |
| RF-056.14 | Ao trocar a atração no seletor, todos os dados exibidos na tela (KPIs, tabelas, gráficos) devem ser atualizados para refletir a atração selecionada |
| RF-056.15 | O Parceiro Comercial não deve ter acesso a atrações de outros Parceiros Comerciais; o seletor deve exibir apenas as atrações vinculadas ao seu próprio perfil |
| RF-056.16 | O sistema deve exibir o nome da atração atualmente selecionada de forma destacada no seletor e no cabeçalho da tela de conteúdo |

Editor

| ID        | Requisito |
|-----------|-----------|
| RF-056.17 | Após o login, o sistema deve direcionar o Editor para a tela Totais da Atração (RF-004) da atração à qual foi vinculado |
| RF-056.18 | O menu lateral do Editor deve conter os seguintes módulos: Totais da Atração, Validar Ingresso, Pesquisar Ingresso, Editar Atração, Gestão de Ingressos, Categorias, Gestão de Cupons, Gráficos Analytics, Perfil |
| RF-056.19 | O Editor deve visualizar exclusivamente os dados da atração à qual foi vinculado por um Parceiro Comercial via RF-021; não deve ser exibido seletor de atração |
| RF-056.20 | O nome da atração vinculada deve ser exibido de forma fixa no cabeçalho ou subtítulo da interface do Editor |
| RF-056.21 | O Editor não deve ter acesso aos módulos de gestão financeira (Relatórios da Atração, Negociação Financeira, Resumo de Despesas) nem ao módulo de Usuários da Atração |

Leitor

| ID        | Requisito |
|-----------|-----------|
| RF-056.22 | Após o login, o sistema deve direcionar o Leitor para a tela Validar Ingresso (RF-025) da atração à qual foi vinculado |
| RF-056.23 | O menu lateral do Leitor deve conter os seguintes módulos: Validar Ingresso, Pesquisar Ingresso, Perfil |
| RF-056.24 | O Leitor deve visualizar exclusivamente os dados da atração à qual foi vinculado por um Parceiro Comercial via RF-021; não deve ser exibido seletor de atração |
| RF-056.25 | Todos os dados visíveis ao Leitor devem ser somente leitura; o perfil não possui permissão para criar, editar ou excluir nenhum registro |
| RF-056.26 | O nome da atração vinculada deve ser exibido de forma fixa no cabeçalho ou subtítulo da interface do Leitor |

Agência

| ID        | Requisito |
|-----------|-----------|
| RF-056.27 | Após o login, o sistema deve direcionar a Agência para a tela Operação Comercial (RF-047) |
| RF-056.28 | O menu lateral da Agência deve conter os seguintes módulos: Operação Comercial, Comissionamento e Repasse, Gestão de Agentes, Perfil |
| RF-056.29 | A tela Operação Comercial acessada pelo perfil Agência deve exibir dados consolidados de suas próprias vendas e das vendas de todos os seus Agentes vinculados, conforme regras de RF-047 |
| RF-056.30 | O módulo Gestão de Agentes (RF-046) acessado pelo perfil Agência deve exibir apenas os Agentes vinculados à sua própria empresa, sem visibilidade sobre agentes de outras agências |
| RF-056.31 | O perfil Agência não deve ter acesso aos módulos exclusivos do Parceiro Comercial, do Editor, do Leitor nem ao painel de Administrador |

Agente

| ID        | Requisito |
|-----------|-----------|
| RF-056.32 | Após o login, o sistema deve direcionar o Agente para a tela Operação Comercial (RF-047) |
| RF-056.33 | O menu lateral do Agente deve conter os seguintes módulos: Operação Comercial, Comissionamento e Repasse, Perfil |
| RF-056.34 | A tela Operação Comercial acessada pelo perfil Agente deve exibir exclusivamente os dados das suas próprias vendas, sem visibilidade sobre vendas de outros Agentes da mesma Agência |
| RF-056.35 | O perfil Agente não deve ter acesso ao módulo Gestão de Agentes; este módulo é exclusivo do perfil Agência e do Administrador |
| RF-056.36 | O Comissionamento e Repasse acessado pelo Agente deve exibir exclusivamente suas próprias comissões, sem dados financeiros de outros Agentes ou da Agência |

Tabela de Menus por Perfil

| Perfil | Módulos Disponíveis | Tela Inicial (Landing) |
|--------|--------------------|-----------------------|
| Parceiro Comercial | Totais da Atração (RF-004), Pesquisar Ingresso (RF-015/016), Gestão de Ingressos (RF-017), Gestão de Cupons (RF-018), Gráficos e Analytics (RF-019), Editar Atração (RF-020), Usuários da Atração (RF-021), Relatórios da Atração (RF-022), Negociação Financeira (RF-023), Resumo de Despesas (RF-024), Perfil (RF-005) | Totais da Atração (RF-004) — primeira atração vinculada |
| Editor | Totais da Atração (RF-004), Validar Ingresso (RF-025), Pesquisar Ingresso (RF-015/016), Editar Atração (RF-020), Gestão de Ingressos (RF-017), Categorias (RF-014), Gestão de Cupons (RF-018), Gráficos Analytics (RF-019), Perfil (RF-005) | Totais da Atração (RF-004) |
| Leitor | Validar Ingresso (RF-025), Pesquisar Ingresso (RF-015/016), Perfil (RF-005) | Validar Ingresso (RF-025) |
| Agência | Operação Comercial (RF-047), Comissionamento e Repasse (RF-048), Gestão de Agentes (RF-046), Perfil (RF-005) | Operação Comercial (RF-047) |
| Agente | Operação Comercial (RF-047), Comissionamento e Repasse (RF-048), Perfil (RF-005) | Operação Comercial (RF-047) |

Regras de Negócio

| ID        | Regra |
|-----------|-------|
| RN-056.01 | O menu lateral exibe exclusivamente os módulos do perfil logado; nenhum perfil enxerga módulos de outro perfil |
| RN-056.02 | O Parceiro Comercial acessa apenas as atrações diretamente vinculadas ao seu perfil no sistema; atrações de outros parceiros são invisíveis |
| RN-056.03 | Quando o Parceiro Comercial possuir múltiplas atrações vinculadas, a primeira atração cadastrada é exibida por padrão; o seletor permite alternar entre elas |
| RN-056.04 | O Editor está vinculado a exatamente uma atração (conforme RF-021) e não possui seletor de atração; sua visão é sempre restrita à atração de vínculo |
| RN-056.05 | O Leitor está vinculado a exatamente uma atração (conforme RF-021) e possui acesso somente leitura; não é possível criar, editar ou excluir qualquer dado |
| RN-056.06 | O Agente visualiza exclusivamente seus próprios dados de vendas e comissões; não há acesso consolidado a dados de outros Agentes nem da Agência |
| RN-056.07 | A Agência visualiza seus próprios dados e os dados consolidados de todos os Agentes vinculados a ela; não visualiza dados de outras agências |
| RN-056.08 | Nenhum dos perfis definidos neste RF tem acesso ao Dashboard do Administrador (RF-003), à Gestão Global de Usuários (RF-006), à Gestão de Contratos (RF-008), às Configurações Comerciais (RF-010) nem à Gestão Global de Atrações (RF-012) |
| RN-056.09 | O sistema deve validar o perfil do usuário no momento do login e redirecionar para a tela de aterrissagem correta; qualquer tentativa de acesso direto a URL de módulo restrito deve redirecionar para a tela inicial do perfil com mensagem de acesso negado |
| RN-056.10 | A desativação de um usuário (feita pelo Administrador ou Parceiro Comercial via RF-021) deve invalidar imediatamente sua sessão ativa, caso exista |
| RN-056.11 | O estado recolhido/expandido do menu lateral deve ser persistido entre as sessões do mesmo usuário via preferência salva no perfil |
| RN-056.12 | O seletor de atração do Parceiro Comercial não é exibido quando o perfil possui apenas uma atração vinculada |
| RN-056.13 | Este RF complementa RF-002 e não o substitui; o Administrador continua sendo governado por RF-002 e RF-003; qualquer alteração no comportamento do Administrador deve ser registrada naqueles documentos |
| RN-056.14 | O perfil Agência pode ativar e inativar seus próprios Agentes via RF-046, mas não pode criar novos perfis de Agência nem alterar perfis do Administrador |

Critérios de Aceitação

| ID        | Critério | Resultado Esperado |
|-----------|----------|--------------------|
| CA-056.01 | Realizar login com credenciais de Parceiro Comercial com uma única atração vinculada | Sistema redireciona para Totais da Atração (RF-004); menu lateral exibe os 11 módulos do perfil; seletor de atração não é exibido |
| CA-056.02 | Realizar login com credenciais de Parceiro Comercial com múltiplas atrações vinculadas | Sistema redireciona para Totais da Atração da primeira atração; seletor de atração é exibido no topo; menu lateral exibe os 11 módulos do perfil |
| CA-056.03 | Trocar a atração no seletor do Parceiro Comercial | Todos os KPIs, tabelas e gráficos da tela são atualizados para refletir os dados da atração recém-selecionada |
| CA-056.04 | Realizar login com credenciais de Editor | Sistema redireciona para Totais da Atração (RF-004); menu lateral exibe os 9 módulos do perfil; seletor de atração não é exibido; nome da atração vinculada aparece no cabeçalho |
| CA-056.05 | Editor tenta acessar por URL direta a tela de Usuários da Atração (RF-021) | Sistema redireciona para a tela inicial do Editor com mensagem de acesso negado |
| CA-056.06 | Realizar login com credenciais de Leitor | Sistema redireciona para Validar Ingresso (RF-025); menu lateral exibe os 3 módulos do perfil; nenhum botão de criação ou edição é exibido |
| CA-056.07 | Leitor tenta acessar por URL direta a tela de Editar Atração (RF-020) | Sistema redireciona para a tela inicial do Leitor com mensagem de acesso negado |
| CA-056.08 | Realizar login com credenciais de Agência | Sistema redireciona para Operação Comercial (RF-047); menu lateral exibe os 4 módulos do perfil; dados consolidados de vendas próprias e dos Agentes vinculados são exibidos |
| CA-056.09 | Realizar login com credenciais de Agente | Sistema redireciona para Operação Comercial (RF-047); menu lateral exibe os 3 módulos do perfil; apenas as vendas do próprio Agente são exibidas |
| CA-056.10 | Agente tenta acessar por URL direta a tela de Gestão de Agentes (RF-046) | Sistema redireciona para a tela inicial do Agente com mensagem de acesso negado |
| CA-056.11 | Clicar em "Sair" em qualquer perfil | Pop-up de confirmação é exibido com opções "Confirmar" e "Cancelar"; ao confirmar, sessão é encerrada e usuário é redirecionado para a tela de login |
| CA-056.12 | Recolher o menu lateral e navegar para outra tela | Menu permanece recolhido; ao reexpandir, exibe os rótulos completos dos módulos |
| CA-056.13 | Administrador desativa um usuário com sessão ativa | A sessão do usuário desativado é invalidada imediatamente; no próximo acesso o sistema exibe mensagem de conta inativa |
| CA-056.14 | Verificar nome de perfil exibido no cabeçalho para cada perfil | O cabeçalho exibe corretamente: "Parceiro Comercial", "Editor", "Leitor", "Agência" ou "Agente" conforme o perfil logado |
| CA-056.15 | Parceiro Comercial tenta acessar por URL direta o Dashboard do Administrador (RF-003) | Sistema redireciona para a tela inicial do Parceiro Comercial com mensagem de acesso negado |

Protótipo/Wireframe

Figura - WF-060 - Tela Inicial por Perfil (Backoffice).png (a definir)
