### 10.11 CU-040 - Gestão de Parceiros Comerciais

ID: CU-040

Nome: Gestão de Parceiros Comerciais

Ator Principal: Administrador

Atores Secundários: Sistema (notificações por e-mail, módulo de Contratos RF-008, Editores e Leitores vinculados, auto-cadastro RF-053)

Pré-condições: Usuário autenticado com perfil Administrador; existirem Parceiros Comerciais cadastrados no sistema

Pós-condições: Status dos parceiros selecionados atualizado (Ativa, Pendente, Suspensa, Inativa ou Excluído) ou, no caso de solicitação de documentação, mantido como "Pendente de Aprovação"; Editores e Leitores vinculados refletem o novo estado (bloqueados na suspensão e na exclusão, liberados na reativação); e-mails enviados; rascunho de Contrato de Atração gerado em RF-008 quando aplicável, com as atrações vinculadas permanecendo no Substatus "Bloqueado para Vendas" até a ativação do contrato no DocuSign (RN-057.15)

Requisitos Relacionados: RF-057

Fluxo Principal:

1. O ator acessa o módulo "Gestão de Parceiros Comerciais".
2. O sistema exibe a tela com a aba "Ativas" selecionada por padrão e a tabela de parceiros ordenada por ID decrescente.
3. O ator pode utilizar o campo de busca (Razão Social, Nome Fantasia, CNPJ ou e-mail), aplicar filtros avançados (Status, Data, Cidade/UF, Qtd Atrações, Segmento) ou alternar entre as abas "Ativas", "Pendente de Aprovação", "Suspensas", "Inativas" e "Todas".
4. O ator seleciona um ou mais parceiros via checkbox; o sistema exibe a barra de ações contextual conforme a aba ativa.
5. O ator escolhe uma ação (Aprovar, Rejeitar, Suspender, Reativar, Inativar, Excluir, Solicitar Documentação Pendente ou Editar) e o sistema exibe o modal de confirmação correspondente.
6. O ator confirma a ação; para Aprovar, Rejeitar, Suspender, Reativar, Inativar e Excluir, o sistema atualiza o status e dispara as notificações por e-mail (incluindo credenciais de acesso, no caso de aprovação), gerando automaticamente um rascunho de Contrato de Atração em RF-008 na aprovação; para Solicitar Documentação Pendente, o sistema mantém o status "Pendente de Aprovação" e apenas envia a notificação ao responsável, registrando a solicitação no histórico do parceiro.
7. O sistema exibe mensagem de sucesso e atualiza a lista; quando há suspensão/reativação, os Editores e Leitores vinculados têm seus acessos bloqueados ou restabelecidos automaticamente; quando há exclusão, os Editores e Leitores vinculados têm o acesso bloqueado automaticamente (RN-057.18).

Fluxos de Exceção:

3a. Auto-cadastro recém-recebido (RF-053) com status "Pendente de Aprovação": Sistema notifica o(s) Administrador(es) por e-mail e via notificação interna, sinalizando o novo cadastro a analisar.
5a. Tentativa de "Editar" com mais de um parceiro selecionado: Sistema mantém o botão desabilitado.
5b. Tentativa de confirmar "Solicitar Documentação Pendente" sem informar a descrição da pendência: Sistema exibe mensagem de erro e impede a confirmação.
6a. Rejeição sem motivo preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6b. Falha no envio de e-mail aos responsáveis (boas-vindas, rejeição, etc.): Sistema mantém a alteração de status, registra o erro no log e notifica o Administrador.
6c. Falha na geração do rascunho de Contrato de Atração (RF-008) após aprovação: Sistema mantém a aprovação, exibe alerta e oferece nova tentativa manual.
