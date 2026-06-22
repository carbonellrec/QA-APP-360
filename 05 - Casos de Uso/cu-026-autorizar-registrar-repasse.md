### 5.26 CU-026 - Autorizar/Registrar Repasse

ID: CU-026

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador; despesa de repasse com status Pendente

Pós-condições: Status da despesa alterado para Autorizado

Requisitos Relacionados: RF-024

Fluxo Principal:

1. O ator acessa Resumo das Despesas (ou lista de despesas pendentes).
2. O sistema exibe as despesas com status Pendente.
3. O ator altera o status da despesa de repasse de Pendente para Autorizado (e registra pagamento se aplicável).
4. O sistema atualiza o status na tabela detalhada e exibe confirmação.
