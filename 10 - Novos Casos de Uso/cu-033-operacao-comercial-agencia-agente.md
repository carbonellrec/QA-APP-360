### 10.4 CU-033 - Operação Comercial - Agência e Agente

ID: CU-033

Nome: Operação Comercial - Agência e Agente

Ator Principal: Agência (suas vendas e dos agentes vinculados); Agente (apenas suas vendas); Administrador (visão global)

Atores Secundários: Sistema (cálculo de KPIs e comissões — RF-010, exportação, envio de e-mail ao turista, fila de reembolsos RF-049, módulo de cupons RF-018)

Pré-condições: Usuário autenticado com perfil Agência, Agente ou Administrador; existirem transações registradas

Pós-condições: KPIs e tabela de transações exibidos conforme filtros e perfil; cancelamentos efetivados quando aplicável (≤ 24h); arquivos exportados quando solicitado

Requisitos Relacionados: RF-047

Fluxo Principal:

1. O ator acessa o painel "Operação Comercial".
2. O sistema exibe título, filtros (período, atração e — conforme o perfil — agente/agência), KPIs (Total de Vendas, Qtd Ingressos, Comissão Acumulada, Cupons) e a tabela de transações.
3. O ator aplica os filtros desejados; o sistema atualiza KPIs e tabela em tempo real.
4. O ator pode clicar em uma linha da tabela para abrir o modal de detalhes da transação (dados do turista, ingresso, pagamento, comissão, status, QR Code e histórico).
5. O ator pode clicar em "Cancelar Venda" (apenas pedidos Confirmados com até 24h da venda) e informar o motivo no modal de confirmação.
6. O sistema invalida o ingresso, estorna a comissão do período e envia e-mail ao turista com o motivo do cancelamento.
7. O ator pode acessar a seção de Cupons para visualizar os cupons da agência ou clicar em "Gerar novo cupom" (fluxo de RF-018).
8. O ator pode clicar em "Exportar" e escolher CSV ou PDF; o sistema gera o arquivo com as transações filtradas.

Fluxos de Exceção:

5a. Pedido com mais de 24h: Botão "Cancelar Venda" não é exibido; sistema orienta encaminhamento via fila de reembolsos do Backoffice (RF-049).
5b. Tentativa de cancelar pedido já Cancelado/Reembolsado: Sistema não exibe a opção.
6a. Motivo de cancelamento não preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6b. Falha no estorno pelo gateway: Sistema mantém o pedido, registra o erro e exibe alerta para reprocessamento.
8a. Falha na geração do arquivo de exportação: Sistema exibe mensagem de erro e oferece nova tentativa.
