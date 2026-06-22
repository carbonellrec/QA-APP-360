### 5.6 CU-006 - Cadastrar Usuário

ID: CU-006

Nome: Cadastrar Usuário

Ator Principal: Administrador

Pré-condições: Usuário autenticado com perfil Administrador

Pós-condições: Novo usuário cadastrado no sistema com perfil e dados definidos

Requisitos Relacionados: RF-007

Fluxo Principal:

1. O ator acessa Gestão de Usuários e clica em adicionar/cadastrar usuário.
2. O sistema exibe o modal de cadastro com campos comuns e campos dinâmicos por perfil.
3. O ator preenche os dados e seleciona o perfil.
4. O ator preenche os campos obrigatórios e confirma.
5. O sistema valida (e-mail único, etc.) e salva o usuário.
6. O sistema exibe confirmação e atualiza a lista.

Fluxos de Exceção:

5a. E-mail já cadastrado: Sistema exibe mensagem de erro e mantém o modal.
5b. Campos obrigatórios faltando: Sistema exibe validação e impede o salvamento.
