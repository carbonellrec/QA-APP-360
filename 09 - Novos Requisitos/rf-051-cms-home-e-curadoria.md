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
| RF-051.11 | O sistema deve permitir reordenar banners via drag-and-drop; a ordem é salva imediatamente                                                                      |
| RF-051.12 | O sistema deve permitir editar todos os campos de um banner existente                                                                                           |
| RF-051.13 | O sistema deve permitir excluir banner com modal de confirmação                                                                                                 |
| RF-051.14 | O sistema deve atualizar automaticamente o status de banners com data de fim expirada para "Expirado" (não exibidos no portal)                                  |
| RF-051.15 | O sistema deve limitar o número de banners simultâneos ativos no carrossel (padrão: 5); banners acima do limite não são exibidos                                |

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
| RF-051.24 | No modo **Automático**, o sistema seleciona automaticamente as 5 avaliações Google mais recentes com classificação ≥ 4 estrelas              |
| RF-051.25 | No modo **Manual**, o Admin pode visualizar as avaliações disponíveis da integração Google para cada atração e selecionar até 5              |
| RF-051.26 | O sistema deve exibir toggle por atração para alternar entre modo Automático e Manual                                                         |
| RF-051.27 | O sistema deve exibir configuração de periodicidade de sincronização com Google: Diária ou Semanal                                            |
| RF-051.28 | O sistema deve exibir indicador de status da última sincronização: data/hora + resultado (Sucesso / Erro com mensagem)                       |
| RF-051.29 | As avaliações curadas são exibidas na página de detalhes da atração correspondente no portal (RF-032)                                        |

Seção 4 — Cross-sell "Outras Atrações"

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-051.30 | O sistema deve exibir lista de atrações com configuração de cross-sell (modo: Automático ou Manual)                                   |
| RF-051.31 | Ao selecionar uma atração-origem, o sistema deve exibir interface para buscar e adicionar atrações sugeridas                          |
| RF-051.32 | O sistema deve permitir definir a ordem das atrações sugeridas                                                                        |
| RF-051.33 | O sistema deve exibir toggle por atração para alternar entre modo Automático e Manual                                                  |
| RF-051.34 | No modo **Automático**, o sistema sugere atrações da mesma categoria ou por proximidade geográfica                                    |
| RF-051.35 | A configuração **Manual** tem prioridade sobre o modo Automático quando ambos estão definidos                                         |
| RF-051.36 | O sistema deve exibir botão "Limpar curadoria manual" que remove a configuração manual e retorna ao modo Automático para aquela atração |
| RF-051.37 | A configuração de "Outras Atrações" é exibida na página de detalhes da atração no portal (RF-032)                                    |

Feedbacks e Confirmações

| ID        | Requisito                                                                                             |
|-----------|-------------------------------------------------------------------------------------------------------|
| RF-051.38 | O sistema deve exibir modal de confirmação antes de publicar alterações em qualquer seção            |
| RF-051.39 | O sistema deve exibir mensagem de sucesso após cada publicação confirmada                             |

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
| RN-051.02 | Banners são exibidos no portal somente se Status = Ativo **E** período de exibição vigente (data atual entre início e fim)                  |
| RN-051.03 | Banner com data de fim expirada tem status atualizado automaticamente para "Expirado"; não é exibido no portal                              |
| RN-051.04 | O número máximo de banners simultâneos no carrossel é configurável pelo Admin (padrão: 5); banners além do limite não são exibidos           |
| RN-051.05 | Imagens de banner: JPEG/PNG/WEBP; máx **3 MB** (desktop) e **1,5 MB** (mobile); ambas as versões são obrigatórias                          |
| RN-051.06 | A seção "Imperdíveis" é **ocultada** no portal quando a lista estiver vazia                                                                  |
| RN-051.07 | Cross-sell: se a curadoria manual estiver vazia para uma atração, o sistema usa o fallback automático por categoria                          |
| RN-051.08 | A integração Google sincroniza apenas avaliações com classificação ≥ **4 estrelas**                                                          |
| RN-051.09 | Alterações publicadas são aplicadas **imediatamente** ao portal, sem fila de aprovação adicional                                             |
| RN-051.10 | A ordem dos banners no carrossel é determinada pelo campo "Ordem" (menor número = primeiro exibido)                                          |

Critérios de Aceitação

| ID        | Critério                                                                               | Resultado Esperado                                                                                     |
|-----------|----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| CA-051.01 | Acessar módulo CMS Home e Curadoria como Administrador                                 | Sub-menu com 4 abas exibido; data da última publicação visível em cada seção                           |
| CA-051.02 | Criar novo banner sem imagem mobile                                                    | Mensagem de erro: campo obrigatório; banner não criado                                                 |
| CA-051.03 | Criar banner com imagem desktop > 3 MB                                                 | Mensagem de erro: "Arquivo excede o limite de 3 MB"                                                    |
| CA-051.04 | Criar banner válido com período agendado futuro                                        | Banner criado com status "Agendado"; não exibido no portal até a data de início                        |
| CA-051.05 | Aguardar a data de fim de um banner passar                                             | Status atualizado automaticamente para "Expirado"; banner removido do carrossel do portal              |
| CA-051.06 | Reordenar banners via drag-and-drop                                                    | Nova ordem refletida no carrossel do portal após salvar                                                |
| CA-051.07 | Adicionar atração à seção "Imperdíveis"                                                | Atração exibida na seção correspondente no portal                                                      |
| CA-051.08 | Remover todas as atrações da seção "Imperdíveis"                                       | Seção "Imperdíveis" oculta no portal                                                                   |
| CA-051.09 | Configurar curadoria Google como "Automático" para uma atração                         | Sistema seleciona as 5 avaliações com ≥ 4 estrelas automaticamente                                    |
| CA-051.10 | Configurar curadoria Google como "Manual" e selecionar 3 avaliações                   | Apenas as 3 avaliações selecionadas exibidas na página de detalhes da atração no portal                |
| CA-051.11 | Verificar indicador de última sincronização Google após sincronização bem-sucedida     | Data/hora da sincronização exibida com status "Sucesso"                                                |
| CA-051.12 | Configurar cross-sell manual para uma atração                                          | Atrações sugeridas configuradas manualmente exibidas na seção "Outras Atrações" da atração no portal   |
| CA-051.13 | Clicar em "Limpar curadoria manual" em uma atração com cross-sell configurado          | Configuração manual removida; sistema retorna ao modo automático para aquela atração                   |
| CA-051.14 | Publicar alterações de banner                                                          | Modal de confirmação exibido; ao confirmar: carrossel atualizado imediatamente no portal               |
| CA-051.15 | Adicionar mais de 6 atrações à seção "Imperdíveis"                                    | Mensagem de aviso: limite máximo atingido; atração excedente não adicionada                            |
| CA-051.16 | Inativar um banner ativo                                                               | Banner removido imediatamente do carrossel do portal                                                   |

Protótipo/Wireframe

Figura - WF-055 - CMS Home - Banners.png (a definir)
