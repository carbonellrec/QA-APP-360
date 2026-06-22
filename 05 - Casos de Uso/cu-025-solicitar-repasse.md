### 5.25 CU-025 - Solicitar Repasse

ID: CU-025

Nome: Solicitar Repasse

Ator Principal: Parceiro Comercial

Pré-condições: Usuário autenticado como Parceiro Comercial; valor disponível para repasse; prazo de pagamento respeitado

Pós-condições: Solicitação de repasse registrada com duas despesas em status Pendente

Requisitos Relacionados: RF-024

Fluxo Principal:

1. O ator acessa Resumo das Despesas e seleciona a atração.
2. O ator clica em Solicitar Repasse.
3. O sistema exibe o modal com valor disponível para repasse.
4. O ator pode clicar em Valor Total para preencher o valor máximo ou informar valor menor.
5. O ator confirma a solicitação.
6. status Pendente.
7. O sistema atualiza a tabela detalhada e exibe confirmação.

Fluxos de Exceção:

6a. Valor maior que disponível: Sistema exibe erro e impede confirmação.

6b. Prazo de pagamento não respeitado: Sistema impede ou exibe mensagem com prazo restante.
