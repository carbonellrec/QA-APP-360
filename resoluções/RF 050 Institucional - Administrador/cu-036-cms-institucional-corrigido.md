### 10.7 CU-036 - CMS Institucional

ID: CU-036

Nome: CMS Institucional

Ator Principal: Administrador

Atores Secundários: Sistema (sanitização XSS no backend, controle de versões, Portal Público, Storage de mídia)

Pré-condições: Usuário autenticado com perfil Administrador

Pós-condições: Conteúdo das páginas institucionais (Política de Privacidade, Condições de Uso, FAQ, Sobre Nós) salvo como rascunho ou publicado no Portal Público; histórico de versões atualizado somente quando houver publicação explícita

Requisitos Relacionados: RF-050

Fluxo Principal:

1. O ator acessa "Conteúdo > Institucional" no menu lateral.
2. O sistema exibe sub-menu com 4 seções (Política de Privacidade, Condições de Uso, FAQ, Sobre Nós), data/autor da última publicação e indicador de rascunho não publicado, quando aplicável.
3. O ator seleciona a seção desejada e edita o conteúdo no editor correspondente (WYSIWYG para Política e Condições; gerenciamento de Categorias/Perguntas para FAQ; campos estruturados de Missão/Visão/Valores, Em Números, Equipe, Parceiros e Banner CTA para Sobre Nós).
4. O ator pode clicar em "Salvar rascunho" para preservar alterações sem afetar o portal, ou em "Pré-visualizar" para abrir nova aba simulando a página. O salvamento de rascunho não gera nova entrada no histórico de versões — o rascunho é uma linha única sobrescrita a cada acionamento.
5. O ator clica em "Publicar"; o sistema exibe modal de confirmação.
6. Ao confirmar, o backend sanitiza o conteúdo (removendo tags `<script>` e atributos de evento inline, independentemente do canal de envio), persiste o conteúdo limpo no banco de dados, publica imediatamente no portal, registra nova entrada no histórico de publicações e exibe mensagem de sucesso.
7. O ator pode acessar o histórico (últimas 20 publicações oficiais) e clicar em "Restaurar"; o sistema salva a versão corrente como rascunho e aplica a versão restaurada ao editor.

Fluxos de Exceção:

3a. (FAQ) Tentativa de excluir categoria com perguntas vinculadas: Sistema bloqueia a exclusão e orienta mover ou excluir as perguntas primeiro.
3b. (Sobre Nós) Upload de imagem fora do padrão (formato diferente de JPEG/PNG/WEBP ou tamanho > 2 MB): Sistema rejeita o arquivo e exibe mensagem de erro.
3c. (FAQ) Criação de categoria com nome que gera slug já existente no sistema: Sistema detecta a duplicidade e atribui automaticamente sufixo numérico incremental ao slug (ex.: "ingressos-1"), prosseguindo com o salvamento sem interromper o fluxo.
3d. (Sobre Nós) Substituição de foto de membro da equipe ou logo de parceiro: Sistema exclui permanentemente o arquivo anterior do Storage antes de persistir o novo, evitando acúmulo de arquivos órfãos.
6a. Conteúdo contém código malicioso (`<script>` ou eventos inline): O backend remove os trechos não permitidos via sanitização e prossegue com a publicação do conteúdo limpo; o ator não é interrompido, mas pode ser notificado que ajustes de formatação foram aplicados automaticamente.
6b. Falha na publicação: Sistema mantém a versão anterior do portal, registra o erro e exibe mensagem para nova tentativa.
