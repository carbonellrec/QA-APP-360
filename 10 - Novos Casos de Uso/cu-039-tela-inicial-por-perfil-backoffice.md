### 10.10 CU-039 - Tela Inicial por Perfil - Backoffice

ID: CU-039

Nome: Tela Inicial por Perfil - Backoffice

Ator Principal: Parceiro Comercial, Editor, Leitor, Agência, Agente

Atores Secundários: Sistema (autenticação, controle de permissões, persistência de preferências de UI)

Pré-condições: Usuário autenticado com um dos perfis: Parceiro Comercial, Editor, Leitor, Agência ou Agente; vínculos com atrações/agência configurados conforme o perfil

Pós-condições: Usuário direcionado à tela inicial correta do seu perfil; menu lateral exibe somente os módulos permitidos; estado de navegação e preferências de UI mantidos durante a sessão

Requisitos Relacionados: RF-056

Fluxo Principal:

1. O ator informa credenciais válidas na tela de login (RF-001).
2. O sistema autentica e identifica o perfil do usuário.
3. O sistema redireciona automaticamente o ator para a tela inicial correspondente:
   - **Parceiro Comercial** → Totais da Atração (RF-004) da primeira atração vinculada;
   - **Editor** → Totais da Atração (RF-004) da atração vinculada;
   - **Leitor** → Validar Ingresso (RF-025) da atração vinculada;
   - **Agência** → Operação Comercial (RF-047);
   - **Agente** → Operação Comercial (RF-047).
4. O sistema exibe no cabeçalho o nome completo, avatar/foto, nome do perfil e o botão "Sair".
5. O sistema renderiza o menu lateral contendo exclusivamente os módulos do perfil logado, com o item da tela atual destacado e respeitando o estado recolhido/expandido persistido do usuário.
6. Quando aplicável (Parceiro Comercial com mais de uma atração), o sistema exibe o seletor de atração no topo; ao trocar a atração, todos os KPIs, tabelas e gráficos da tela são atualizados.
7. O ator navega pelos módulos disponíveis; ao clicar em "Sair", o sistema exibe pop-up de confirmação e, ao confirmar, encerra a sessão e redireciona à tela de login.

Fluxos de Exceção:

3a. Tentativa de acesso direto via URL a módulo restrito (ex.: Editor → RF-021, Agente → RF-046, Parceiro Comercial → RF-003): Sistema redireciona para a tela inicial do perfil e exibe mensagem de acesso negado.
3b. Parceiro Comercial sem atrações vinculadas: Sistema exibe mensagem informativa e oculta o seletor; módulos dependentes de atração ficam indisponíveis.
4a. Usuário desativado pelo Administrador (ou Parceiro Comercial via RF-021) durante a sessão: Sistema invalida a sessão imediatamente e, no próximo acesso, exibe mensagem de conta inativa.
6a. Troca de atração com falha de carregamento: Sistema mantém a atração anterior, exibe mensagem de erro e oferece nova tentativa.
7a. Cancelamento da confirmação de logout: Sistema mantém a sessão ativa e a tela atual.
