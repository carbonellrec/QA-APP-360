### 10.5 CU-034 - Comissionamento e Repasse - Agência e Agente

ID: CU-034

Nome: Comissionamento e Repasse - Agência e Agente

Ator Principal: Agência (solicita repasses e contesta), Administrador (fecha período, autoriza ou rejeita repasses, resolve contestações), Agente (apenas visualização)

Atores Secundários: Sistema (consolidação de comissões, notificações, integrações de RF-010, RF-045 e RF-047)

Pré-condições: Usuário autenticado com perfil Agência, Agente ou Administrador; existirem comissões geradas no período corrente ou em períodos fechados

Pós-condições: Períodos consolidados/fechados conforme regras; solicitações de repasse criadas e processadas; contestações registradas e resolvidas; notificações disparadas aos perfis envolvidos

Requisitos Relacionados: RF-048

Fluxo Principal:

1. O ator acessa o painel de Comissionamento e Repasse correspondente ao seu perfil.
2. O sistema exibe o resumo do período atual (Comissão Bruta, Deduções, Comissão Líquida) e a tabela de histórico de períodos com badge de status.
3. A Agência clica em uma linha do histórico e o sistema expande o detalhamento por atração e por agente vinculado.
4. A Agência aciona "Solicitar Repasse" em períodos com status "Fechado" e comissão líquida > 0; o sistema abre o modal com período, valor, dados bancários e campo opcional de observação.
5. A Agência confirma a solicitação; o sistema altera o status do período para "Repasse Solicitado" e notifica o Administrador.
6. O Administrador acessa "Gestão de Repasses", filtra/seleciona a solicitação e clica em "Autorizar Repasse"; informa data e, opcionalmente, comprovante.
7. Ao confirmar a autorização, o sistema altera o status para "Repasse Pago" e notifica a Agência.
8. Mensalmente (ou sob demanda), o Administrador aciona "Fechar Período"; o sistema consolida vendas, aplica deduções e altera o status para "Fechado", iniciando novo período em aberto.

Fluxos de Exceção:

4a. Tentativa de solicitar repasse de período "Aguardando Fechamento": Botão não é exibido/é desabilitado.
4b. Dados bancários desatualizados: Modal exibe link "Atualizar dados bancários" que redireciona à RF-045.
5a. Agência opta por contestar: Sistema abre formulário de contestação com lista de transações; ao enviar, status muda para "Em Contestação" e Administrador é notificado. Tentativa de contestar período com status "Repasse Pago" é bloqueada com mensagem informativa.
6a. Administrador rejeita a solicitação: Sistema exige motivo, retorna o status para "Fechado" e notifica a Agência com a justificativa.
8a. Vendas canceladas após o fechamento: Dedução é compensada automaticamente no próximo período de apuração.
8b. Tentativa de alterar comissões já consolidadas: Sistema bloqueia a operação e exibe mensagem de período encerrado.
