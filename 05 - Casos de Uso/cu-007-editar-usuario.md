### 5.7 CU-007 - Editar Usuário

ID: CU-007

Nome: Editar Usuário

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador; usuário a editar existente

Pós-condições: Dados do usuário atualizados no sistema

Requisitos Relacionados: RF-007

Fluxo Principal:

1. O ator acessa Gestão de Usuários, seleciona um usuário e clica em Editar.
2. O sistema exibe o modal em modo edição com dados preenchidos.
3. O ator altera os campos desejados e confirma.
4. O sistema valida e salva.
5. O sistema exibe confirmação e atualiza a lista.

Fluxos de Exceção:

4a. Validação falha: Sistema exibe mensagem e mantém o modal.
