### 10.5 CU-034 - Comissionamento e Repasse - Agência e Agente

ID: CU-034

Nome: Comissionamento e Repasse - Agência e Agente

Ator Principal: Agência (solicita repasses e contesta), Administrador (fecha período, autoriza ou rejeita repasses, resolve contestações e reportes de divergência, aplica lançamentos avulsos), Agente (visualização e reporte de divergência)

Atores Secundários: Sistema (consolidação de comissões, notificações, integrações de RF-010, RF-045, RF-046 e RF-047)

Pré-condições: Usuário autenticado com perfil Agência, Agente ou Administrador; existirem comissões geradas no período corrente ou em períodos fechados

Pós-condições: Períodos consolidados/fechados conforme regras; solicitações de repasse criadas e processadas; contestações e reportes de divergência registrados e resolvidos; lançamentos avulsos aplicados quando necessário; notificações disparadas aos perfis envolvidos, incluindo Agentes ao receberem confirmação de repasse

Requisitos Relacionados: RF-048

Fluxo Principal:

1. O ator acessa o painel de Comissionamento e Repasse correspondente ao seu perfil.
2. O sistema exibe o resumo do período atual (Comissão Bruta, Deduções, Comissão Líquida) e a tabela de histórico de períodos com badge de status.
3. A Agência clica em uma linha do histórico e o sistema expande o detalhamento por atração e por agente vinculado, oferecendo também a visão expansível por transação individual com totalizador de conferência (Valor da Venda x Valor da Comissão), sinalizando eventuais divergências de percentual enquanto o período estiver "Aguardando Fechamento".
4. A Agência aciona "Solicitar Repasse" em períodos com status "Fechado" e comissão líquida > 0; o sistema abre o modal com período, valor, dados bancários e campo opcional de observação.
5. A Agência confirma a solicitação; o sistema altera o status do período para "Repasse Solicitado" e notifica o Administrador.
6. O Administrador acessa "Gestão de Repasses", filtra/seleciona a solicitação e clica em "Autorizar Repasse"; informa data e, opcionalmente, comprovante.
7. Ao confirmar a autorização, o sistema altera o status para "Repasse Pago", notifica a Agência e envia notificação informativa a cada Agente vinculado ao período, comunicando que o repasse foi processado.
8. Mensalmente (ou sob demanda), o Administrador aciona "Fechar Período"; o sistema consolida vendas, aplica deduções e altera o status para "Fechado", iniciando novo período em aberto.
9. O Agente, ao identificar uma possível divergência em sua comissão individual, pode clicar em "Reportar Divergência" em qualquer transação de período "Fechado" ou "Repasse Solicitado", informando motivo e, opcionalmente, o valor esperado; o sistema registra o reporte com status "Reportada" e notifica o Administrador e a Agência vinculada.
10. O Administrador resolve a contestação da Agência ou o reporte de divergência do Agente como Aprovada Total, Aprovada Parcialmente ou Rejeitada, notificando as partes envolvidas.

Fluxos de Exceção:

4a. Tentativa de solicitar repasse de período "Aguardando Fechamento": Botão não é exibido/é desabilitado.
4b. Dados bancários desatualizados: Modal exibe link "Atualizar dados bancários" que redireciona à RF-045.
5a. Agência opta por contestar: Sistema abre formulário de contestação com lista de transações; ao enviar, status muda para "Em Contestação" e Administrador é notificado. Tentativa de contestar período com status "Repasse Pago" é bloqueada com mensagem informativa, orientando o uso do lançamento avulso (RF-048.39) pelo Administrador.
6a. Administrador rejeita a solicitação: Sistema exige motivo, retorna o status para "Fechado" e notifica a Agência com a justificativa.
8a. Vendas canceladas após o fechamento (período ainda não pago): Dedução é compensada automaticamente no próximo período de apuração.
8b. Tentativa de alterar comissões já consolidadas: Sistema bloqueia a operação e exibe mensagem de período encerrado.
8c. Vendas canceladas após o período já estar com status "Repasse Pago": Dedução/débito é registrada no próximo período de apuração em aberto, sem alteração retroativa do período pago.
9a. Agente tenta reportar divergência em período com status "Repasse Pago": Sistema não exibe a opção; orienta que correções nesse cenário são tratadas exclusivamente pelo Administrador via lançamento avulso.
9b. Agente reporta divergência sem preencher o motivo: Sistema exibe mensagem de erro e impede o envio do reporte.
10a. Administrador identifica erro em período "Repasse Pago" (via contestação retroativa relatada informalmente, auditoria ou reporte de Agente referente a período já pago): Sistema não permite reabertura do período original; Administrador aplica Lançamento Avulso de Crédito ou Débito no período de apuração subsequente em aberto, informando valor, motivo e período de referência da correção; Agência e, se aplicável, Agente são notificados.
