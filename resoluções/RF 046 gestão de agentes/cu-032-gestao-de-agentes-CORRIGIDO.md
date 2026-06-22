### 10.3 CU-032 - Gestão de Agentes

ID: CU-032

Nome: Gestão de Agentes

Ator Principal: Administrador (visão global); Agência (apenas seus próprios agentes)

Atores Secundários: Sistema (validação de CPF/e-mail, controle de vínculos, histórico de comissionamento, bloqueio/desbloqueio em cascata por status da agência — RF-044)

Pré-condições: Usuário autenticado com perfil Administrador ou Agência; existirem agentes ou agências cadastradas

Pós-condições: Agentes cadastrados, atualizados, ativados, inativados, transferidos (Admin) ou desvinculados (Agência); vínculos com agência atualizados; histórico de comissões preservado e vinculado de forma irrevogável à agência de origem das vendas; status dos agentes refletindo automaticamente eventuais bloqueios ou liberações em cascata decorrentes de alterações de status da agência vinculada (inativação, reativação ou exclusão)

Requisitos Relacionados: RF-046

Fluxo Principal:

1. O ator acessa "Gestão de Agentes" (Admin) ou "Meus Agentes" (Agência).
2. O sistema exibe a tela com a aba "Ativos" selecionada e a tabela filtrada conforme o perfil (lista global para Admin; restrita à própria agência para Agência).
3. O ator pode buscar por nome, CPF ou e-mail (busca case-insensitive), aplicar filtros avançados e alternar entre as abas "Ativos", "Inativos" e "Todos".
4. O ator clica em "Adicionar Agente" para cadastrar/vincular um novo agente, ou seleciona agentes existentes via checkbox para acionar ações em massa.
5. No cadastro/edição, o sistema exibe o modal com foto, dados pessoais, idioma, agência vinculada e atrações autorizadas; o ator preenche os campos e confirma.
6. O sistema valida unicidade de CPF e e-mail, persiste os dados e atualiza a listagem.
7. Para ações em massa (Editar — apenas 1 selecionado, Inativar/Ativar, Excluir, Transferir para outra Agência ou Desvincular), o sistema exibe modal de confirmação correspondente. Na transferência, o sistema permite selecionar agentes ativos ou inativos; se algum agente estiver inativo, o modal informa que ele será reativado automaticamente na agência de destino.
8. O ator confirma a ação e o sistema atualiza o status/vínculo dos agentes selecionados, mantendo o histórico de comissões anterior vinculado de forma irrevogável à agência de origem (em caso de transferência) e preservando as vendas já realizadas como pertencentes à agência de origem.
9. O sistema exibe mensagem de sucesso e atualiza a tabela.

Fluxos de Exceção:

5a. CPF inválido (dígito verificador): Sistema exibe mensagem e bloqueia o salvamento.
5b. CPF pertencente a agente em soft delete: Sistema permite o novo cadastro, sujeitando-o à análise do Administrador antes da liberação (RN-046.16).
6a. E-mail já cadastrado: Sistema exibe "E-mail já cadastrado no sistema" e impede o salvamento.
7a. Tentativa de "Editar" com mais de 1 agente selecionado: Botão permanece desabilitado.
7b. Perfil Agência tenta acionar "Excluir" ou "Transferir para outra Agência": Sistema não exibe essas ações para o perfil Agência.
7c. Tentativa de "Ativar" ou "Editar" um agente cuja inatividade decorre de bloqueio em cascata por agência inativa: Sistema mantém os botões desabilitados até que a agência seja reativada ou o agente seja transferido para outra agência ativa.
8a. Falha na transferência (agência de destino inativa ou sem contrato vigente no RF-008): Sistema exibe mensagem e cancela a operação, mantendo o vínculo original.
8b. Agência vinculada a um ou mais agentes é inativada (evento originado em RF-044): Sistema altera automaticamente, em cascata, o status de todos os agentes vinculados para "Inativo (Agência Bloqueada)", bloqueando login e impedindo novas vendas.
8c. Agência vinculada a agentes bloqueados por cascata é reativada com contrato ativo no RF-008 (evento originado em RF-044): Sistema restabelece automaticamente o status "Ativo" apenas dos agentes que estavam inativos exclusivamente por efeito da cascata, preservando como "Inativo" os agentes que já haviam sido inativados manualmente antes do bloqueio.
8d. Agência vinculada a agentes é excluída via soft delete (evento originado em RF-044): Sistema aplica soft delete em cascata a todos os agentes vinculados, preservando histórico financeiro e estatístico para fins de auditoria, sem afetar comissões já fechadas e pendentes de pagamento.
