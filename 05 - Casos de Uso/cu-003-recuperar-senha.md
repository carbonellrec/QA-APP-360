### 5.3 CU-003 - Recuperar Senha

ID: CU-003

Nome: Recuperar Senha

Ator Principal: Usuário

Atores Secundários: Sistema (envio de e-mail)

Pré-condições: E-mail cadastrado no sistema

Pós-condições: Usuário com nova senha definida

Requisitos Relacionados: RF-001

Fluxo Principal:

1. O ator acessa a tela de login e clica em "Esqueci minha senha".
2. O sistema exibe campo para informar o e-mail.
3. O ator informa o e-mail de cadastro.
4. O sistema envia link ou senha temporária para o e-mail.
5. O ator acessa o link ou insere a senha temporária e define nova senha.
6. O sistema confirma a alteração e redireciona para a tela de login.

Fluxos de Exceção:

4a. E-mail não cadastrado: Sistema exibe mensagem genérica ou informa que o e-mail não foi encontrado.
