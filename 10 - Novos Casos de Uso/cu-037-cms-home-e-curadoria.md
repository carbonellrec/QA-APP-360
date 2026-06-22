### 10.8 CU-037 - CMS Home e Curadoria

ID: CU-037

Nome: CMS Home e Curadoria

Ator Principal: Administrador

Atores Secundários: Sistema (integração Google para avaliações, Portal Público RF-026 e RF-032)

Pré-condições: Usuário autenticado com perfil Administrador; existirem atrações cadastradas no sistema

Pós-condições: Banners do carrossel, destaques "Imperdíveis", curadoria de avaliações Google e cross-sell "Outras Atrações" configurados e publicados imediatamente no Portal Público

Requisitos Relacionados: RF-051

Fluxo Principal:

1. O ator acessa "Conteúdo > Home e Curadoria" no menu lateral.
2. O sistema exibe as 4 abas (Banners, Destaques "Imperdíveis", Curadoria Google, Outras Atrações), painel de status com data da última publicação por seção e indicador de alterações não publicadas.
3. O ator seleciona a aba desejada:
   - **Banners**: visualiza a lista, clica em "Novo Banner" e preenche imagens (Desktop 1280px e Mobile 375px), título, subtítulo, CTA, link, datas de início/fim, status e ordem; pode editar, reordenar via drag-and-drop ou excluir banners existentes.
   - **Imperdíveis**: busca atrações cadastradas, adiciona até 6 itens, reordena ou remove.
   - **Curadoria Google**: alterna o modo (Automático/Manual) por atração, configura periodicidade de sincronização e, no modo Manual, seleciona até 5 avaliações.
   - **Outras Atrações**: alterna o modo (Automático/Manual) por atração, define manualmente as atrações sugeridas e a ordem.
4. O ator clica em "Salvar e Publicar" (ou equivalente da seção); o sistema exibe modal de confirmação.
5. Ao confirmar, o sistema aplica as alterações imediatamente ao Portal Público (RF-026 / RF-032) e exibe mensagem de sucesso.
6. O sistema atualiza automaticamente o status dos banners conforme as datas configuradas (Ativo, Agendado, Expirado, Inativo).

Fluxos de Exceção:

3a. Upload de imagem de banner sem versão Mobile ou acima do tamanho permitido (Desktop > 3 MB ou Mobile > 1,5 MB): Sistema exibe mensagem de erro e bloqueia o salvamento.
3b. Tentativa de adicionar mais de 6 atrações em "Imperdíveis": Sistema exibe aviso de limite e não adiciona o item excedente.
3c. Lista de "Imperdíveis" vazia: Seção é ocultada no Portal Público.
3d. Falha na sincronização Google: Sistema exibe status "Erro" com a mensagem retornada e mantém as avaliações anteriores.
3e. Curadoria manual de cross-sell vazia: Sistema aplica o fallback automático por categoria/proximidade.
4a. Banner com data de fim expirada: Sistema atualiza automaticamente o status para "Expirado" e remove do carrossel sem ação do Admin.
