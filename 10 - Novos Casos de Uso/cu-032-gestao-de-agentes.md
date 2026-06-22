### 10.3 CU-032 - Gestão de Agentes

ID: CU-032

Nome: Gestão de Agentes

Ator Principal: Administrador (visão global); Agência (apenas seus próprios agentes)

Atores Secundários: Sistema (validação de CPF/e-mail, controle de vínculos, histórico de comissionamento)

Pré-condições: Usuário autenticado com perfil Administrador ou Agência; existirem agentes ou agências cadastradas

Pós-condições: Agentes cadastrados, atualizados, ativados, inativados, transferidos (Admin) ou desvinculados (Agência); vínculos com agência atualizados; histórico de comissões preservado

Requisitos Relacionados: RF-046

Fluxo Principal:

1. O ator acessa "Gestão de Agentes" (Admin) ou "Meus Agentes" (Agência).
2. O sistema exibe a tela com a aba "Ativos" selecionada e a tabela filtrada conforme o perfil (lista global para Admin; restrita à própria agência para Agência).
3. O ator pode buscar por nome, CPF ou e-mail, aplicar filtros avançados e alternar entre as abas "Ativos", "Inativos" e "Todos".
4. O ator clica em "Adicionar Agente" para cadastrar/vincular um novo agente, ou seleciona agentes existentes via checkbox para acionar ações em massa.
5. No cadastro/edição, o sistema exibe o modal com foto, dados pessoais, idioma, agência vinculada e atrações autorizadas; o ator preenche os campos e confirma.
6. O sistema valida unicidade de CPF e e-mail, persiste os dados e atualiza a listagem.
7. Para ações em massa (Editar — apenas 1 selecionado, Inativar/Ativar, Excluir, Transferir para outra Agência ou Desvincular), o sistema exibe modal de confirmação correspondente.
8. O ator confirma a ação e o sistema atualiza o status/vínculo dos agentes selecionados, mantendo o histórico de comissões anterior vinculado à agência de origem (em caso de transferência).
9. O sistema exibe mensagem de sucesso e atualiza a tabela.

Fluxos de Exceção:

5a. CPF inválido (dígito verificador): Sistema exibe mensagem e bloqueia o salvamento.
6a. E-mail já cadastrado: Sistema exibe "E-mail já cadastrado no sistema" e impede o salvamento.
7a. Tentativa de "Editar" com mais de 1 agente selecionado: Botão permanece desabilitado.
7b. Perfil Agência tenta acionar "Excluir" ou "Transferir para outra Agência": Sistema não exibe essas ações para o perfil Agência.
8a. Falha na transferência (agência de destino inativa): Sistema exibe mensagem e cancela a operação, mantendo o vínculo original.
