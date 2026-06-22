### 3.50 CMS Institucional - Administrador

**ID:** RF-050

Módulo: CMS / Conteúdo Institucional

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo de gerenciamento de conteúdo (CMS) para as páginas institucionais exibidas no Portal Público. O Administrador pode editar e publicar Política de Privacidade (RF-041), Condições de Uso (RF-041), FAQ — Perguntas Frequentes (RF-042) e Sobre Nós (RF-043). As alterações publicadas refletem imediatamente nas respectivas páginas do portal.

Requisitos Detalhados

Estrutura Geral e Navegação

| ID        | Requisito                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------|
| RF-050.01 | O sistema deve exibir o módulo CMS Institucional acessível via menu lateral "Conteúdo > Institucional"               |
| RF-050.02 | O módulo deve exibir sub-menu com 4 seções: Política de Privacidade, Condições de Uso, FAQ, Sobre Nós               |
| RF-050.03 | O sistema deve exibir breadcrumb indicando a seção ativa (ex.: "Conteúdo > Institucional > FAQ")                     |
| RF-050.04 | Cada seção deve exibir a data e o autor da última publicação                                                          |
| RF-050.05 | O sistema deve indicar visualmente quando há rascunho não publicado em uma seção                                     |

Editor de Política de Privacidade

| ID        | Requisito                                                                                                                                    |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-050.06 | O sistema deve exibir editor de texto rico (WYSIWYG) com suporte a: H1, H2, H3, parágrafos, listas ordenadas e não ordenadas, negrito, itálico, sublinhado e links |
| RF-050.07 | O sistema deve exibir botão "Salvar rascunho" que salva o conteúdo sem publicar (não afeta o portal)                                        |
| RF-050.08 | O sistema deve exibir botão "Publicar" que aplica o conteúdo imediatamente ao portal após confirmação em modal                              |
| RF-050.09 | O sistema deve exibir botão "Pré-visualizar" que abre preview em nova aba simulando a página no portal                                      |
| RF-050.10 | O sistema deve exibir histórico de versões com as últimas 20 versões publicadas, exibindo: data, autor e botão "Restaurar" — rascunhos intermediários não geram entrada no histórico |
| RF-050.11 | Ao clicar em "Restaurar", o sistema deve salvar a versão corrente como rascunho antes de aplicar a versão restaurada                        |
| RF-050.12 | O sistema deve exibir a data da última publicação no topo do editor                                                                          |
| RF-050.13 | O editor deve sinalizar visualmente tags `<script>` e atributos de evento inline; a sanitização definitiva ocorre no backend antes da persistência no banco de dados |

Editor de Condições de Uso

| ID        | Requisito                                                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------|
| RF-050.14 | O sistema deve exibir editor idêntico ao da Política de Privacidade (RF-050.06 a RF-050.13) para a página Condições de Uso |
| RF-050.15 | O conteúdo de Condições de Uso deve ser independente do conteúdo de Política de Privacidade                             |
| RF-050.16 | O histórico de versões da Condições de Uso deve ser mantido separadamente do histórico da Política                      |
| RF-050.17 | O sistema deve exibir a data da última publicação das Condições de Uso no topo do editor correspondente                 |

Gerenciamento do FAQ — Categorias

| ID        | Requisito                                                                                                                          |
|-----------|------------------------------------------------------------------------------------------------------------------------------------|
| RF-050.18 | O sistema deve exibir lista de categorias do FAQ com colunas: Ordem, Nome, Slug, Qtd Perguntas, Status (Ativa/Inativa)            |
| RF-050.19 | O sistema deve exibir botão "Nova Categoria" que abre modal de criação                                                             |
| RF-050.20 | O modal de nova categoria deve exibir campos: Nome (obrigatório), Slug (auto-gerado a partir do nome, editável), Ordem, Status    |
| RF-050.21 | O sistema deve permitir editar nome, slug, ordem e status de categorias existentes                                                 |
| RF-050.22 | O sistema deve bloquear a exclusão de categoria que possua perguntas vinculadas, exibindo mensagem de orientação                   |
| RF-050.23 | O sistema deve permitir excluir categoria sem perguntas vinculadas, com modal de confirmação                                       |
| RF-050.24 | O sistema deve permitir reordenar categorias via drag-and-drop ou campo de ordem numérico; ao soltar o item, o frontend envia ao backend uma lista completa com a nova ordenação de todas as categorias em uma única requisição |
| RF-050.25 | Categoria com status Inativa não deve ser exibida no Portal Público                                                                |

Gerenciamento do FAQ — Perguntas

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-050.26 | Ao clicar em uma categoria, o sistema deve exibir sub-lista de perguntas com colunas: Ordem, Pergunta (resumida), Status, Ações       |
| RF-050.27 | O sistema deve exibir botão "Nova Pergunta" que abre modal de criação                                                                  |
| RF-050.28 | O modal de nova pergunta deve exibir campos: Categoria, Pergunta (texto, obrigatório), Resposta (editor rico), Ordem, Status           |
| RF-050.29 | O sistema deve permitir editar todos os campos de uma pergunta existente                                                               |
| RF-050.30 | O sistema deve permitir excluir pergunta com modal de confirmação                                                                      |
| RF-050.31 | O sistema deve permitir mover pergunta para outra categoria via campo "Categoria" na edição                                            |
| RF-050.32 | O sistema deve permitir reordenar perguntas dentro da categoria via drag-and-drop; ao soltar o item, o frontend envia ao backend uma lista completa com a nova ordenação de todas as perguntas da categoria em uma única requisição |
| RF-050.33 | Pergunta com status Inativa não deve ser exibida no Portal Público                                                                     |

Editor do Sobre Nós

| ID        | Requisito                                                                                                                                |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------|
| RF-050.34 | O sistema deve exibir campo de texto para edição de Missão, Visão e Valores (3 campos separados)                                        |
| RF-050.35 | O sistema deve permitir CRUD de indicadores numéricos (ex.: "5.000+ ingressos vendidos"), com campos: Label, Valor e Ordem              |
| RF-050.36 | O sistema deve permitir CRUD de membros da equipe com campos: upload de foto (JPEG/PNG/WEBP, máx 2 MB), Nome, Cargo e Ordem            |
| RF-050.37 | O sistema deve permitir CRUD de parceiros com campos: upload de logo (JPEG/PNG/WEBP, máx 2 MB), Nome, Link (opcional) e Ordem          |
| RF-050.38 | O sistema deve exibir campos para edição do Banner CTA: Título, Subtítulo, Texto do botão e Link do botão                              |
| RF-050.39 | O sistema deve exibir botão "Pré-visualizar" que abre preview da página Sobre Nós em nova aba                                          |
| RF-050.40 | O sistema deve exibir botão "Publicar" que aplica todas as alterações do Sobre Nós imediatamente ao portal após confirmação             |
| RF-050.41 | O sistema deve exibir mensagem de sucesso após a publicação bem-sucedida de cada seção                                                  |

Estrutura de Navegação

| Sub-seção               | RF Relacionado | Descrição                                    |
|-------------------------|----------------|----------------------------------------------|
| Política de Privacidade | RF-041         | Exibida no portal como página `/privacidade` |
| Condições de Uso        | RF-041         | Exibida no portal como página `/termos`      |
| FAQ                     | RF-042         | Exibida no portal como página `/faq`         |
| Sobre Nós               | RF-043         | Exibida no portal como página `/sobre`       |

Campos do Modal Nova Categoria

| Campo  | Tipo                 | Obrigatório | Observação                              |
|--------|----------------------|-------------|-----------------------------------------|
| Nome   | Texto                | Sim         | Máx 80 caracteres                       |
| Slug   | Texto                | Sim         | Auto-gerado; deve ser único no sistema  |
| Ordem  | Número inteiro       | Sim         | Menor número = exibido primeiro         |
| Status | Toggle Ativa/Inativa | Sim         | Padrão: Ativa                           |

Campos do Modal Nova Pergunta

| Campo     | Tipo                    | Obrigatório | Observação                             |
|-----------|-------------------------|-------------|----------------------------------------|
| Categoria | Select                  | Sim         | Lista de categorias ativas             |
| Pergunta  | Texto                   | Sim         | Máx 255 caracteres                     |
| Resposta  | Editor rico             | Sim         | Suporta negrito, itálico, listas, links |
| Ordem     | Número inteiro          | Sim         | Ordem dentro da categoria              |
| Status    | Toggle Ativa/Inativa    | Sim         | Padrão: Ativa                          |

Sub-seções do Sobre Nós

| Sub-seção            | Campos Editáveis                         | RF Relacionado |
|----------------------|------------------------------------------|----------------|
| Missão/Visão/Valores | Texto livre por item (3 campos)          | RF-043         |
| Em Números           | Label + Valor + Ordem (CRUD)             | RF-043         |
| Nossa Equipe         | Foto + Nome + Cargo + Ordem (CRUD)       | RF-043         |
| Nossos Parceiros     | Logo + Nome + Link + Ordem (CRUD)        | RF-043         |
| Banner CTA           | Título + Subtítulo + Texto Botão + Link  | RF-043         |

Regras de Negócio

| ID        | Regra                                                                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RN-050.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                           |
| RN-050.02 | A publicação é imediata, sem necessidade de aprovação por outro usuário                                                               |
| RN-050.03 | Rascunho não afeta o conteúdo exibido no portal; somente a publicação explícita atualiza o portal                                    |
| RN-050.04 | O histórico de versões retém as últimas **20 publicações oficiais** por seção (Política, Condições); salvamentos de rascunho não geram nova entrada no histórico — o rascunho é uma linha única sobrescrita a cada "Salvar rascunho" |
| RN-050.05 | Ao restaurar versão anterior, a versão corrente é automaticamente salva como rascunho antes da substituição                          |
| RN-050.06 | A sanitização contra XSS deve ocorrer **no backend**, antes da persistência no banco de dados, utilizando biblioteca consagrada (ex.: Bleach/Python), permitindo apenas as tags: `p`, `b`, `i`, `u`, `h1`, `h2`, `h3`, `ul`, `ol`, `li`, `a` e os atributos `href`, `title` e `target` para a tag `<a>`; tags `<script>` e atributos de evento inline (`onclick`, `onload` etc.) são removidos/bloqueados independentemente do canal de envio |
| RN-050.07 | Categoria do FAQ com perguntas vinculadas **não pode ser excluída** — o sistema exibe mensagem orientando mover ou excluir as perguntas primeiro |
| RN-050.08 | Itens inativos (categoria ou pergunta) não são exibidos no Portal Público                                                            |
| RN-050.09 | Upload de imagens (equipe e parceiros): formatos JPEG/PNG/WEBP, tamanho máximo **2 MB**; sistema rejeita arquivos fora do padrão     |
| RN-050.10 | Slug de categoria é **auto-gerado** a partir do nome (ex.: "Devolução" → "devolucao"), editável manualmente; deve ser único **globalmente no sistema** — em caso de duplicidade, o sistema adiciona automaticamente sufixo numérico incremental (ex.: "ingressos", "ingressos-1", "ingressos-2") |
| RN-050.11 | A data de última atualização exibida na página do portal reflete a data da **publicação** (não a data do rascunho)                   |
| RN-050.12 | Ao atualizar a foto de um membro da equipe ou logo de parceiro (RF-050.36 / RF-050.37), o sistema deve **excluir permanentemente** o arquivo de imagem anterior do Storage, evitando acúmulo de arquivos órfãos |

Critérios de Aceitação

| ID        | Critério                                                                          | Resultado Esperado                                                                              |
|-----------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| CA-050.01 | Acessar CMS Institucional como Administrador                                      | Sub-menu com 4 seções exibido; data da última publicação de cada seção visível                  |
| CA-050.02 | Editar Política de Privacidade e clicar em "Salvar rascunho"                      | Conteúdo salvo sem publicar; portal exibe versão anterior; indicador de rascunho não publicado; histórico de versões não é alterado |
| CA-050.03 | Clicar em "Publicar" na Política de Privacidade                                   | Modal de confirmação exibido; ao confirmar: portal atualizado imediatamente; nova entrada criada no histórico de versões |
| CA-050.04 | Clicar em "Pré-visualizar" na Política de Privacidade                             | Nova aba abre com preview da página no layout do portal                                         |
| CA-050.05 | Restaurar versão anterior da Política de Privacidade                              | Versão corrente salva como rascunho; versão selecionada aplicada ao editor                      |
| CA-050.06 | Tentar inserir `<script>` no editor WYSIWYG e salvar                              | Tag bloqueada e removida pelo backend; conteúdo sanitizado persistido; publicação prossegue sem o trecho malicioso |
| CA-050.07 | Criar nova categoria no FAQ                                                       | Categoria criada com slug auto-gerado; aparece na listagem e no portal se status Ativa          |
| CA-050.08 | Tentar excluir categoria do FAQ com perguntas vinculadas                          | Mensagem de bloqueio exibida; categoria não excluída                                            |
| CA-050.09 | Inativar categoria do FAQ                                                         | Categoria e suas perguntas deixam de aparecer no Portal Público                                 |
| CA-050.10 | Criar nova pergunta no FAQ                                                        | Pergunta criada e exibida no portal na categoria selecionada                                    |
| CA-050.11 | Inativar uma pergunta do FAQ                                                      | Pergunta não aparece mais no Portal Público; demais perguntas mantidas                          |
| CA-050.12 | Reordenar perguntas via drag-and-drop                                             | Nova ordem refletida no portal após publicação; backend recebe lista completa em uma única requisição |
| CA-050.13 | Upload de foto de membro da equipe com arquivo PNG de 1,5 MB                     | Upload realizado com sucesso; imagem exibida na pré-visualização                                |
| CA-050.14 | Tentativa de upload de imagem com 3 MB                                            | Mensagem de erro: "Arquivo excede o limite de 2 MB"                                             |
| CA-050.15 | Publicar alterações na seção Sobre Nós                                            | Modal de confirmação exibido; ao confirmar: página Sobre Nós no portal atualizada imediatamente |
| CA-050.16 | Criar duas categorias com o mesmo nome "Ingressos"                                | Primeira categoria recebe slug "ingressos"; segunda recebe slug "ingressos-1" automaticamente   |
| CA-050.17 | Salvar rascunho 5 vezes seguidas sem publicar e verificar histórico               | Histórico permanece inalterado; o rascunho sobrescreve a linha de rascunho anterior sem criar novas entradas |

Protótipo/Wireframe

Figura - WF-054 - CMS Institucional.png (a definir)
