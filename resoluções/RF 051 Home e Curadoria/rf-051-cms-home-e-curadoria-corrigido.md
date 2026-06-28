### 3.51 CMS Home e Curadoria - Administrador

**ID:** RF-051

Módulo: CMS / Home e Curadoria

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo do Backoffice para configurar o conteúdo dinâmico e as seções curadas da Home do Portal Público (RF-026), incluindo o gerenciamento de banners do carrossel, seleção manual de destaques "Imperdíveis", curadoria de avaliações Google por atração (RF-032) e configuração do cross-sell "Outras Atrações" (RF-032). Alterações publicadas refletem imediatamente no portal.

Requisitos Detalhados

Estrutura Geral e Navegação

| ID        | Requisito                                                                                                                          |
|-----------|------------------------------------------------------------------------------------------------------------------------------------|
| RF-051.01 | O sistema deve exibir o módulo acessível via menu lateral "Conteúdo > Home e Curadoria"                                           |
| RF-051.02 | O módulo deve exibir sub-menu com 4 abas: Banners, Destaques "Imperdíveis", Curadoria Google, Outras Atrações                    |
| RF-051.03 | O sistema deve exibir painel de status mostrando a data da última publicação de cada seção                                        |
| RF-051.04 | O sistema deve exibir indicador visual quando há alterações não publicadas em uma aba                                              |
| RF-051.05 | O sistema deve exibir mensagem de sucesso após a publicação de qualquer seção                                                      |

Seção 1 — Banners do Carrossel

| ID        | Requisito                                                                                                                                                       |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RF-051.06 | O sistema deve exibir lista de banners com colunas: Ordem, Pré-visualização (miniatura 80px), Título, CTA, Período (início - fim), Status                       |
| RF-051.07 | Os status possíveis de um banner são: Ativo, Inativo, Agendado (período futuro), Expirado (data fim passada)                                                    |
| RF-051.08 | O sistema deve exibir botão "Novo Banner" que abre modal de criação                                                                                             |
| RF-051.09 | O modal de novo banner deve exibir campo de upload de imagem Desktop (1280px, obrigatório) e imagem Mobile (375px, obrigatório)                                 |
| RF-051.10 | O modal de novo banner deve exibir campos: Título (opcional), Subtítulo (opcional), Texto do botão CTA, Link do CTA, Data de Início, Data de Fim, Status, Ordem |
| RF-051.11 | O sistema deve permitir reordenar banners via drag-and-drop; ao soltar o item, o frontend envia ao backend uma lista completa com a nova ordenação de todos os banners em uma única requisição |
| RF-051.12 | O sistema deve permitir editar todos os campos de um banner existente                                                                                           |
| RF-051.13 | O sistema deve permitir excluir banner com modal de confirmação                                                                                                 |
| RF-051.14 | A exibição de banners no portal é determinada dinamicamente no momento da requisição, validando se a data atual está dentro do período de vigência (data_inicio ≤ agora ≤ data_fim); o status "Expirado" é atualizado por rotina automatizada (Cron Job) para fins de controle no painel, sem que isso afete a lógica de exibição do portal |
| RF-051.15 | O sistema deve bloquear no backend o agendamento ou ativação de banner cujo período de vigência resulte em mais de 5 banners simultâneos ativos; a validação verifica sobreposição de janelas temporais antes de persistir |

Seção 2 — Destaques "Imperdíveis"

| ID        | Requisito                                                                                                                       |
|-----------|---------------------------------------------------------------------------------------------------------------------------------|
| RF-051.16 | O sistema deve exibir campo de busca para selecionar atrações cadastradas no sistema                                           |
| RF-051.17 | O sistema deve exibir lista das atrações selecionadas para a seção "Imperdíveis" com indicador de ordem                       |
| RF-051.18 | O sistema deve permitir reordenar atrações via drag-and-drop                                                                   |
| RF-051.19 | O sistema deve exibir botão "Remover" por atração selecionada                                                                  |
| RF-051.20 | O sistema deve limitar o máximo de atrações na seção (padrão: 6)                                                               |
| RF-051.21 | A seção "Imperdíveis" deve ser ocultada no portal se a lista estiver vazia                                                     |
| RF-051.22 | O sistema deve exibir botão "Salvar e Publicar" que aplica a configuração imediatamente ao portal                              |

Seção 3 — Curadoria de Avaliações Google

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-051.23 | O sistema deve exibir lista de atrações com o modo de curadoria Google configurado para cada uma (Automático ou Manual)                      |
| RF-051.24 | No modo **Automático**, o sistema seleciona automaticamente as 5 avaliações mais recentes disponíveis no cache local com classificação ≥ 4 estrelas |
| RF-051.25 | No modo **Manual**, o Admin pode visualizar as avaliações disponíveis no cache local para cada atração e selecionar até 5                    |
| RF-051.26 | O sistema deve exibir toggle por atração para alternar entre modo Automático e Manual                                                         |
| RF-051.27 | O sistema deve exibir configuração de periodicidade de sincronização com Google: Diária ou Semanal                                            |
| RF-051.28 | O sistema deve exibir indicador de status da última sincronização: data/hora + resultado (Sucesso / Erro com mensagem)                       |
| RF-051.29 | As avaliações curadas são exibidas na página de detalhes da atração correspondente no portal (RF-032); o portal consome exclusivamente os dados do cache local, nunca chamando a API do Google diretamente |

Seção 4 — Cross-sell "Outras Atrações"

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-051.30 | O sistema deve exibir lista de atrações com configuração de cross-sell (modo: Automático ou Manual)                                   |
| RF-051.31 | Ao selecionar uma atração-origem, o sistema deve exibir interface para buscar e adicionar atrações sugeridas                          |
| RF-051.32 | O sistema deve permitir definir a ordem das atrações sugeridas                                                                        |
| RF-051.33 | O sistema deve exibir toggle por atração para alternar entre modo Automático e Manual                                                  |
| RF-051.34 | No modo **Automático**, o sistema sugere no máximo 4 atrações, priorizando primeiro atrações da mesma categoria e, como critério de desempate, menor distância geográfica (raio máximo de 50 km) |
| RF-051.35 | No modo **Manual**, o Admin define quais atrações são sugeridas e em que ordem                                                        |
| RF-051.36 | O sistema deve exibir botão "Limpar curadoria manual" por atração, retornando ao modo automático                                      |
| RF-051.37 | O sistema deve exibir botão "Salvar e Publicar" que aplica as configurações de cross-sell imediatamente ao portal                     |

Seções e RF Relacionado

| Seção                     | RF do Portal | Onde é Exibida                                  |
|---------------------------|--------------|-------------------------------------------------|
| Banners do Carrossel      | RF-026       | Carrossel na Home do Portal Público             |
| Destaques "Imperdíveis"   | RF-026       | Seção "Imperdíveis" na Home                     |
| Curadoria Google          | RF-032       | Avaliações na página de detalhes da atração     |
| Outras Atrações           | RF-032       | Seção "Outras Atrações" na página de detalhes   |

Campos do Modal Novo Banner

| Campo          | Tipo                   | Obrigatório | Observação                                         |
|----------------|------------------------|-------------|----------------------------------------------------|
| Imagem Desktop | Upload (JPEG/PNG/WEBP) | Sim         | Dimensão 1280px, máx 3 MB                          |
| Imagem Mobile  | Upload (JPEG/PNG/WEBP) | Sim         | Dimensão 375px, máx 1,5 MB                         |
| Título         | Texto                  | Não         | Sobreposto à imagem; máx 80 caracteres             |
| Subtítulo      | Texto                  | Não         | Máx 120 caracteres                                 |
| Texto CTA      | Texto                  | Sim         | Texto do botão; máx 40 caracteres                  |
| Link CTA       | URL                    | Sim         | Interna (ex.: /atracao/slug) ou externa (https://) |
| Data de Início | Data/hora              | Não         | Se vazio: exibido imediatamente                    |
| Data de Fim    | Data/hora              | Não         | Se vazio: sem expiração                            |
| Status         | Toggle Ativo/Inativo   | Sim         | Padrão: Ativo                                      |
| Ordem          | Número inteiro         | Sim         | Menor número = exibido primeiro                    |

Status dos Banners

| Status    | Condição                                            | Exibido no Portal |
|-----------|-----------------------------------------------------|-------------------|
| Ativo     | Status Ativo + período vigente ou sem data definida | Sim               |
| Agendado  | Status Ativo + data de início futura                | Não (ainda)       |
| Expirado  | Data de fim passada                                 | Não               |
| Inativo   | Status definido como Inativo manualmente            | Não               |

Regras de Negócio

| ID        | Regra                                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| RN-051.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                                   |
| RN-051.02 | Banners são exibidos no portal somente se Status = Ativo **E** período de exibição vigente (data atual entre início e fim), validado dinamicamente na query da API pública no momento da requisição |
| RN-051.03 | A expiração de banners no portal é baseada no **tempo da requisição** (data_inicio ≤ now() ≤ data_fim), não em gatilho manual do painel; uma rotina automatizada (Cron Job) atualiza a coluna de status para "Expirado" no banco de dados periodicamente para fins de exibição no painel administrativo |
| RN-051.04 | O número máximo de banners simultâneos no carrossel é 5; o backend **valida a sobreposição de janelas temporais** antes de persistir qualquer novo banner ou edição — se o período informado resultar em mais de 5 banners simultâneos, a operação é bloqueada com mensagem de erro |
| RN-051.05 | Imagens de banner: JPEG/PNG/WEBP; máx **3 MB** (desktop) e **1,5 MB** (mobile); ambas as versões são obrigatórias                          |
| RN-051.06 | A seção "Imperdíveis" é **ocultada** no portal quando a lista estiver vazia                                                                  |
| RN-051.07 | Cross-sell: se a curadoria manual estiver vazia para uma atração, o sistema usa o fallback automático por categoria/proximidade geográfica (conforme RN-051.12) |
| RN-051.08 | A integração Google sincroniza apenas avaliações com classificação ≥ **4 estrelas**; as avaliações obtidas são armazenadas em cache local no banco de dados antes de qualquer uso no portal |
| RN-051.09 | Alterações publicadas são aplicadas **imediatamente** ao portal, sem fila de aprovação adicional                                             |
| RN-051.10 | A ordem dos banners no carrossel é determinada pelo campo "Ordem" (menor número = primeiro exibido)                                          |
| RN-051.11 | **[NOVO]** Para fins de performance e controle de custos com API de terceiros, todas as avaliações obtidas da API do Google Places são armazenadas em tabela de cache local no banco de dados; a exibição no portal consome exclusivamente os dados cacheados, respeitando a periodicidade de atualização configurada (RF-051.27); a API do Google nunca é chamada diretamente no fluxo de requisição do portal |
| RN-051.12 | **[NOVO]** Quando o cross-sell estiver operando no modo Automático (RN-051.07), o sistema retorna no máximo **4 atrações sugeridas**, priorizando primeiro atrações da mesma categoria e, como segundo critério de desempate, a menor distância geográfica (raio máximo de **50 km**) |
| RN-051.13 | Monitoramento de falha de sincronização Google: caso a sincronização não obtenha sucesso por um período equivalente a 3 ciclos consecutivos da periodicidade configurada (3 dias para sincronização Diária; 21 dias para sincronização Semanal), o sistema deve exibir alerta no painel administrativo informando a data da última sincronização bem-sucedida. As avaliações do cache permanecem exibidas no portal sem interrupção — a decisão de ocultá-las fica a cargo do Administrador via toggle manual na interface. A data da última atualização das avaliações não é exibida ao turista. |

Critérios de Aceitação

| ID        | Critério                                                                               | Resultado Esperado                                                                                     |
|-----------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| CA-051.01 | Acessar módulo CMS Home e Curadoria como Administrador                                 | Sub-menu com 4 abas exibido; data da última publicação visível em cada seção                           |
| CA-051.02 | Criar novo banner sem imagem mobile                                                    | Mensagem de erro: campo obrigatório; banner não criado                                                 |
| CA-051.03 | Criar banner com imagem desktop > 3 MB                                                 | Mensagem de erro: "Arquivo excede o limite de 3 MB"                                                    |
| CA-051.04 | Criar banner válido com período agendado futuro                                        | Banner criado com status "Agendado"; não exibido no portal até a data de início                        |
| CA-051.05 | Aguardar a data de fim de um banner passar                                             | Banner removido do carrossel do portal imediatamente (validação dinâmica na query); status atualizado para "Expirado" no painel pela rotina automatizada |
| CA-051.06 | Reordenar banners via drag-and-drop                                                    | Nova ordem refletida no carrossel do portal após salvar; backend recebe lista completa em uma única requisição |
| CA-051.07 | Adicionar atração à seção "Imperdíveis"                                                | Atração exibida na seção correspondente no portal                                                      |
| CA-051.08 | Remover todas as atrações da seção "Imperdíveis"                                       | Seção "Imperdíveis" oculta no portal                                                                   |
| CA-051.09 | Configurar curadoria Google como "Automático" para uma atração                         | Sistema seleciona as 5 avaliações com ≥ 4 estrelas do cache local automaticamente                     |
| CA-051.10 | Configurar curadoria Google como "Manual" e selecionar 3 avaliações                   | Apenas as 3 avaliações selecionadas exibidas na página de detalhes da atração no portal                |
| CA-051.11 | Verificar indicador de última sincronização Google após sincronização bem-sucedida     | Data/hora da sincronização exibida com status "Sucesso"                                                |
| CA-051.12 | Configurar cross-sell manual para uma atração                                          | Atrações sugeridas configuradas manualmente exibidas na seção "Outras Atrações" da atração no portal   |
| CA-051.13 | Clicar em "Limpar curadoria manual" em uma atração com cross-sell configurado          | Configuração manual removida; sistema retorna ao modo automático para aquela atração                   |
| CA-051.14 | Publicar alterações de banner                                                          | Modal de confirmação exibido; ao confirmar: carrossel atualizado imediatamente no portal               |
| CA-051.15 | Adicionar mais de 6 atrações à seção "Imperdíveis"                                    | Mensagem de aviso: limite máximo atingido; atração excedente não adicionada                            |
| CA-051.16 | Inativar um banner ativo                                                               | Banner removido imediatamente do carrossel do portal                                                   |
| CA-051.17 | **[NOVO]** Tentar agendar um banner cujo período de vigência coincida com outros 5 banners já ativos no sistema | O sistema bloqueia a operação no backend e exibe mensagem de erro alertando sobre o conflito de janelas temporais; banner não persistido |

Protótipo/Wireframe

Figura - WF-055 - CMS Home - Banners.png (a definir)
