### 5.22 CU-022 - Gerenciar Usuários da Atração

ID: CU-022

Nome: Gerenciar Usuários da Atração

Ator Principal: Administrador, Parceiro Comercial

Pré-condições: Usuário autenticado; atração selecionada

Pós-condições: Usuários vinculados à atração (Editor, Leitor, Agência, Agente) cadastrados/editados/desvinculados

Requisitos Relacionados: RF-021, WF-026, WF-027

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Usuários.
2. O sistema exibe a lista de usuários vinculados à atração.
3. O ator pode adicionar usuário (vincular existente ou criar Editor/Leitor no contexto da atração), editar ou desvincular.
4. O sistema valida (não permite vincular Parceiro Comercial nem Turista) e salva.
5. O sistema atualiza a lista.

Fluxos de Exceção:

4a. Tentativa de vincular perfil não permitido: Sistema exibe mensagem e impede.
