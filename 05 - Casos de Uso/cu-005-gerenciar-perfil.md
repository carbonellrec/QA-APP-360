### 5.5 CU-005 - Gerenciar Perfil

ID: CU-005

Nome: Gerenciar Perfil

Ator Principal: Usuário autenticado

Atores Secundários: —

Pré-condições: Usuário autenticado

Pós-condições: Dados do perfil atualizados no sistema; integração Google

Analytics (Parceiro) salva quando aplicável

Requisitos Relacionados: RF-005

Fluxo Principal:

1. O ator acessa o modal de perfil (menu ou ícone).
2. O sistema exibe os dados atuais (nome, e-mail, etc.) e opções exclusivas por perfil.
3. O ator altera os campos desejados e confirma.
4. O sistema valida e salva as alterações.
5. O sistema exibe confirmação de sucesso.

Fluxos de Exceção:

4a. Dados inválidos: Sistema exibe mensagem de validação e mantém o modal aberto.
