### 10.11 CU-040 - Gestão de Parceiros Comerciais

ID: CU-040

Nome: Gestão de Parceiros Comerciais

Ator Principal: Administrador

Atores Secundários: Sistema (notificações por e-mail, módulo de Contratos RF-008, Editores e Leitores vinculados, auto-cadastro RF-053)

Pré-condições: Usuário autenticado com perfil Administrador; existirem Parceiros Comerciais cadastrados no sistema

Pós-condições: Status dos parceiros selecionados atualizado (Ativa, Pendente, Suspensa, Inativa ou Excluído); Editores e Leitores vinculados refletem o novo estado; e-mails enviados; rascunho de Contrato de Atração gerado em RF-008 quando aplicável

Requisitos Relacionados: RF-057

Fluxo Principal:

1. O ator acessa o módulo "Gestão de Parceiros Comerciais".
2. O sistema exibe a tela com a aba "Ativas" selecionada por padrão e a tabela de parceiros ordenada por ID decrescente.
3. O ator pode utilizar o campo de busca (Razão Social, Nome Fantasia, CNPJ ou e-mail), aplicar filtros avançados (Status, Data, Cidade/UF, Qtd Atrações, Segmento) ou alternar entre as abas "Ativas", "Pendente de Aprovação", "Suspensas", "Inativas" e "Todas".
4. O ator seleciona um ou mais parceiros via checkbox; o sistema exibe a barra de ações contextual conforme a aba ativa.
5. O ator escolhe uma ação (Aprovar, Rejeitar, Suspender, Reativar, Inativar, Excluir ou Editar) e o sistema exibe o modal de confirmação correspondente.
6. O ator confirma a ação e o sistema atualiza o status, dispara as notificações por e-mail (incluindo credenciais de acesso, no caso de aprovação) e, na aprovação, gera automaticamente um rascunho de Contrato de Atração em RF-008.
7. O sistema exibe mensagem de sucesso e atualiza a lista; quando há suspensão/reativação, os Editores e Leitores vinculados têm seus acessos bloqueados ou restabelecidos automaticamente.

Fluxos de Exceção:

5a. Tentativa de "Editar" com mais de um parceiro selecionado: Sistema mantém o botão desabilitado.
6a. Rejeição sem motivo preenchido: Sistema exibe mensagem de erro e impede a confirmação.
6b. Falha no envio de e-mail aos responsáveis (boas-vindas, rejeição, etc.): Sistema mantém a alteração de status, registra o erro no log e notifica o Administrador.
6c. Falha na geração do rascunho de Contrato de Atração (RF-008) após aprovação: Sistema mantém a aprovação, exibe alerta e oferece nova tentativa manual.
3a. Auto-cadastro recém-recebido (RF-053) com status "Pendente de Aprovação": Sistema notifica o(s) Administrador(es) por e-mail e via notificação interna, sinalizando o novo cadastro a analisar.
