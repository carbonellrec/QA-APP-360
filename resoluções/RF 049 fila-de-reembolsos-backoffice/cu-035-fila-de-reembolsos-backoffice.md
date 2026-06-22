### 10.6 CU-035 - Fila de Reembolsos - Backoffice

ID: CU-035

Nome: Fila de Reembolsos - Backoffice

Ator Principal: Administrador

Atores Secundários: Sistema (gateway de pagamento, envio de e-mails ao turista, RF-040 para reembolsos automáticos)

Pré-condições: Usuário autenticado com perfil Administrador; existirem solicitações manuais de reembolso (compras com mais de 7 dias e fora da janela de cancelamento gratuito vigente na atração)

Pós-condições: Solicitações analisadas e marcadas como "Em Análise", "Aprovado" (com valor integral ou parcial) ou "Rejeitado"; ingressos invalidados quando aprovados; estornos processados; e-mails enviados ao turista; origem da solicitação registrada (Turista, Agente, Agência ou Administrador); histórico de ações registrado

Requisitos Relacionados: RF-049

Fluxo Principal:

1. O ator acessa o módulo "Fila de Reembolsos".
2. O sistema exibe a tela com a aba "Pendentes" selecionada por padrão, contador de itens pendentes e tabela ordenada por SLA decrescente.
3. O ator pode buscar por ID de reembolso, ID de pedido, nome ou e-mail do turista, aplicar filtros avançados (Status, Período, Atração, Motivo, Faixa de Valor, Origem) e alternar entre as abas.
4. O ator clica em uma linha para abrir o modal de Detalhes e Decisão, com seções: Dados da Solicitação (incluindo origem e, quando aplicável, identificação do solicitante e justificativa operacional), Dados do Ingresso, Motivo informado, Política de Cancelamento da Atração vigente na data da compra e Decisão.
5. O ator analisa as informações e seleciona uma das ações: "Marcar como Em Análise", "Aprovar Reembolso" (com valor integral ou parcial e observação interna) ou "Rejeitar Reembolso" (com motivo obrigatório).
6. Ao aprovar, o sistema invalida o ingresso, processa o estorno via gateway, envia e-mail ao turista com valor e prazo, e altera o status para "Aprovado".
7. Ao rejeitar, o sistema exibe preview do e-mail, envia ao turista o motivo e canal de contestação, e altera o status para "Rejeitado".
8. O sistema registra todas as ações no histórico do modal e atualiza a fila.

Fluxos de Exceção:

2a. Solicitação com até 7 dias da compra: Não aparece na fila; é processada automaticamente via RF-040.
2b. Ingresso com selo/direito de cancelamento gratuito ativo (independentemente do prazo de 7 dias): Sistema desvia o fluxo da fila manual (RF-049), invalida o ingresso imediatamente e dispara o estorno automático via gateway (RF-040).
2c. Cancelamento por iniciativa do Administrador por força maior, overbooking ou segurança técnica: Sistema processa de forma mandatória e imediata, aplicando estorno integral ao turista e cancelamento total de quaisquer comissões provisionadas para a cadeia de intermediários, sem necessidade de transitar pela Fila de Reembolsos.
5a. Ações em massa via checkbox: Sistema exibe barra de ações ("Aprovar selecionados", "Rejeitar selecionados", "Marcar como Em Análise"); rejeição em massa exige motivo único aplicado a todos os selecionados.
5b. Solicitação de origem Agente ou Agência efetuada após o prazo de 7 dias: O modal exibe obrigatoriamente a identificação do usuário solicitante e a justificativa operacional anexada à solicitação.
6a. Aprovação parcial com valor inválido (≤ 0 ou maior que o pago): Sistema exibe mensagem de erro e bloqueia o salvamento.
6b. Falha no estorno pelo gateway: Sistema mantém o status anterior, registra o erro no histórico e exibe alerta para reprocessamento.
7a. Tentativa de rejeitar sem informar motivo: Sistema exibe "Motivo obrigatório" e bloqueia a confirmação.
8a. Tentativa de editar/excluir registros do histórico de ações: Sistema bloqueia a operação para qualquer perfil.
