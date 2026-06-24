### 10.4 CU-033 - Operação Comercial - Agência e Agente

ID: CU-033

Nome: Operação Comercial - Agência e Agente

Ator Principal: Agência (suas vendas e dos agentes vinculados); Agente (apenas suas vendas); Administrador (visão global)

Atores Secundários: Sistema (cálculo de KPIs e comissões — RF-010, exportação, envio de e-mail ao turista, notificação ao agente em caso de cancelamento pela agência, fila de reembolsos RF-049, módulo de cupons RF-018, gateway de pagamento para estorno)

Pré-condições: Usuário autenticado com perfil Agência, Agente ou Administrador; existirem transações registradas

Pós-condições: KPIs e tabela de transações exibidos conforme filtros e perfil; cancelamentos (totais ou parciais) efetivados quando aplicável (≤ 24h), com estorno processado e ingresso(s) invalidado(s); turista e, quando aplicável, agente notificados; arquivos exportados quando solicitado

Requisitos Relacionados: RF-047

Fluxo Principal:

1. O ator acessa o painel "Operação Comercial".
2. O sistema exibe título, filtros (período, atração e — conforme o perfil — agente/agência/qtd. de cancelamentos), KPIs (Total de Vendas, Qtd Ingressos, Comissão Acumulada, Cupons, Qtd de Vendas Canceladas/Reembolsadas) e a tabela de transações.
3. O ator aplica os filtros desejados; o sistema atualiza KPIs e tabela em tempo real.
4. O ator pode clicar em uma linha da tabela para abrir o modal de detalhes da transação (dados do turista, ingresso(s) individuais com QR Code próprio, pagamento, comissão, status, histórico).
5. O ator pode clicar em "Cancelar Venda" (apenas pedidos com ao menos um ingresso Confirmado e até 24h da venda), selecionar um, vários ou todos os ingressos do pedido e informar o motivo no modal de confirmação. Qualquer um dos três perfis (Agência, Agente ou Administrador) pode executar esta ação, restrito ao escopo de visibilidade de suas próprias vendas (RN-047.01 a RN-047.03).
6. O sistema invalida o(s) ingresso(s) selecionado(s), estorna a comissão proporcionalmente, processa o estorno ao turista via gateway de pagamento, atualiza o status do pedido para "Cancelado Total" ou "Cancelado Parcial" conforme o caso, e envia e-mail ao turista com o motivo e os itens cancelados. Quando o cancelamento for realizado pela Agência sobre a venda de um Agente vinculado, o sistema também notifica o Agente.
7. O ator pode acessar a seção de Cupons para visualizar os cupons da agência ou clicar em "Gerar novo cupom" (fluxo de RF-018).
8. O ator pode clicar em "Exportar" e escolher CSV ou PDF; o sistema gera o arquivo com as transações filtradas.

Fluxos de Exceção:

5a. Pedido com mais de 24h: Botão "Cancelar Venda" não é exibido; sistema orienta encaminhamento via fila de reembolsos do Backoffice (RF-049).
5b. Tentativa de cancelar pedido já Cancelado Total/Reembolsado: Sistema não exibe a opção. Itens já cancelados individualmente dentro de um pedido parcialmente cancelado não podem ser selecionados novamente.
5c. Ator tenta cancelar venda fora do seu escopo de visibilidade (ex.: Agente tentando cancelar venda de outro agente): Sistema não exibe a opção de cancelamento para o pedido fora do escopo.
6a. Motivo de cancelamento não preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6b. Falha no estorno pelo gateway: Sistema mantém o pedido, registra o erro e exibe alerta para reprocessamento; o(s) ingresso(s) não é(são) invalidado(s) até a confirmação do estorno.
6c. Falha no envio da notificação ao Agente (quando o cancelamento for feito pela Agência): Sistema registra o erro no log, mantém o cancelamento efetivado e notifica o Administrador para acompanhamento.
8a. Falha na geração do arquivo de exportação: Sistema exibe mensagem de erro e oferece nova tentativa.
