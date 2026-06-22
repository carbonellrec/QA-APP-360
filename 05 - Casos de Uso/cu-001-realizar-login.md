### 5.1 CU-001 - Realizar Login

ID: CU-001

Nome: Realizar Login

Ator Principal: Usuário (todos os perfis: Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente)

Atores Secundários: Sistema (validação de credenciais)

Pré-condições: Usuário cadastrado no sistema; e-mail e senha registrados

Pós-condições: Usuário autenticado no sistema; redirecionado para a tela inicial conforme perfil

Requisitos Relacionados: RF-001

Fluxo Principal:

1. O ator acessa a tela de login do Backoffice.

O ator informa e-mail e senha.

O sistema valida as credenciais.

O sistema redireciona o ator para a tela inicial (home) de acordo com o perfil de acesso.

Fluxos de Exceção:

3a. Credenciais inválidas: Sistema exibe mensagem de erro e mantém na tela de login.
3b. Usuário inativo: Sistema exibe mensagem informando que o usuário está inativo.
