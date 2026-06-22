### 10.1 CU-030 - Gestão de Agências

ID: CU-030

Nome: Gestão de Agências

Ator Principal: Administrador

Atores Secundários: Sistema (notificações por e-mail, módulo de Contratos RF-008, Agentes vinculados)

Pré-condições: Usuário autenticado com perfil Administrador; existirem agências cadastradas no sistema

Pós-condições: Status das agências selecionadas atualizado (Ativa, Aguardando Contrato, Pendente, Suspensa, Inativa ou Excluída); agentes vinculados refletem o novo estado da agência; e-mails e notificações disparados conforme a ação; log de auditoria registrado quando aplicável

Requisitos Relacionados: RF-044

Fluxo Principal:

1. O ator acessa o módulo "Gestão de Agências".
2. O sistema exibe a tela com a aba "Ativas" selecionada por padrão, listando as agências em ordem decrescente de ID.
3. O ator pode utilizar o campo de busca (Nome Fantasia, CNPJ ou e-mail) de forma case-insensitive e com suporte a CNPJ parcial, aplicar filtros avançados ou alternar entre as abas "Ativas", "Aguardando Contrato", "Pendente de Aprovação", "Suspensas", "Inativas" e "Todas".
4. O ator seleciona uma ou mais agências via checkbox; o sistema exibe a barra de ações contextual conforme a aba ativa.
5. O ator escolhe uma ação (Aprovar, Rejeitar, Suspender, Reativar, Inativar, Excluir, Gerar Contrato ou Editar) e o sistema exibe modal de confirmação correspondente.
6. O ator confirma a ação e o sistema atualiza o status, dispara as notificações por e-mail e, quando aplicável, gera o rascunho de Contrato de Agência em RF-008. Ao aprovar, o status da agência é definido como "Aguardando Contrato" — o status "Ativa" só é concedido após o contrato atingir status "Ativo" no RF-008 (todas as assinaturas via DocuSign coletadas). Ao inativar ou excluir, o sistema aplica o bloqueio/soft delete em cascata nos agentes vinculados.
7. O sistema exibe mensagem de sucesso e atualiza a lista de agências.

Fluxos de Exceção:

5a. Tentativa de "Editar" com mais de uma agência selecionada: Sistema mantém o botão desabilitado e a ação não é executada.
6a. Rejeição sem motivo preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6b. Exclusão sem motivo preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6c. Falha no envio de e-mail aos responsáveis: Sistema registra o erro no log, mantém a alteração de status e notifica o Administrador.
6d. Falha na geração do rascunho de Contrato de Agência (RF-008) após aprovação: Sistema mantém a aprovação com status "Aguardando Contrato", exibe alerta e oferece nova tentativa manual via botão "Gerar Contrato" na aba correspondente.
6e. Reativação de agência inativa com contrato vencido ou inexistente no RF-008: Sistema alerta o Administrador, move a agência para status "Aguardando Contrato" e mantém os agentes bloqueados até que novo ciclo de contrato seja concluído com sucesso.
