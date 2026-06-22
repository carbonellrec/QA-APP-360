### 10.9 CU-038 - Central de Notificações

ID: CU-038

Nome: Central de Notificações

Ator Principal: Administrador

Atores Secundários: Sistema (serviços de envio de e-mail e push, validação de variáveis, integração com preferências de opt-in RF-038, validação de categoria de evento para condição "Obrigatório")

Pré-condições: Usuário autenticado com perfil Administrador

Pós-condições: Templates criados/atualizados; regras de disparo automático configuradas; campanhas criadas (rascunho, imediatas ou agendadas) ou canceladas; histórico de envios disponível para consulta e exportação

Requisitos Relacionados: RF-052

Fluxo Principal:

1. O ator acessa "Notificações" no menu lateral.
2. O sistema exibe sub-menu com 4 abas (Templates, Regras de Disparo, Campanhas, Histórico de Envios), painel de resumo do mês e indicador do status do serviço de envio. O painel de resumo e o indicador de status são **somente leitura** — o ator não realiza nenhuma ação sobre eles nesta etapa.
3. Em **Templates**, o ator pode criar/editar/duplicar/inativar templates de e-mail (assunto, corpo HTML WYSIWYG, variáveis dinâmicas) e push (título, corpo, link, ícone), pré-visualizar (Desktop/Mobile) e enviar e-mail de teste; o sistema valida as variáveis ao salvar.
4. Em **Regras de Disparo**, o ator associa por tipo de evento o canal (E-mail/Push/Ambos), o template, o delay e a condição de opt-in; para eventos **Transacionais**, estão disponíveis as opções "Obrigatório" e "Respeita opt-in"; para eventos de **Marketing/Opt-in**, apenas "Respeita opt-in" está disponível — a opção "Obrigatório" é desabilitada pelo sistema; o ator pode ativar/desativar regras individualmente.
5. Em **Campanhas**, o ator clica em "Nova Campanha", informa nome, tipo, template, segmentação do público-alvo (incluindo opção "Turistas com opt-in ativo para marketing", com estimativa de alcance) e data/hora de envio (Imediato ou Agendado); pode clicar em **"Salvar como Rascunho"** para preservar a configuração sem enviar/agendar, ou confirmar a criação imediata/agendada; campanhas existentes podem ser duplicadas, gerando cópia com status Rascunho.
6. O sistema processa a campanha conforme o agendamento, respeitando opt-ins e o status verificado de e-mail dos turistas; campanhas agendadas podem ser canceladas antes do envio.
7. Em **Histórico de Envios**, o ator pode filtrar (Canal, Status, Evento/Campanha, Período), visualizar status (Enviado, Aberto, Falhou, Bounced) e exportar para CSV.

Fluxos de Exceção:

3a. Variável de template não reconhecida (ex.: `{{campo_inexistente}}`): Sistema exibe mensagem de erro e impede o salvamento.
3b. Título de push acima de 50 caracteres ou corpo acima de 150: Sistema bloqueia a digitação ao atingir o limite.
3c. Upload de ícone push fora do permitido (formato/tamanho > 512 KB): Sistema rejeita o arquivo.
4a. Tentativa de associar template inativo a uma regra: Sistema bloqueia a operação com mensagem de erro.
4b. [NOVO] Tentativa de selecionar a condição "Obrigatório" em regra vinculada a evento de Marketing/Opt-in: Sistema mantém a opção desabilitada/bloqueada na interface; apenas "Respeita opt-in" é selecionável para esses eventos; o ator não consegue contornar a restrição via interface.
5a. Tentativa de criar campanha com template inativo: Sistema exibe "Template inativo não pode ser usado em campanhas".
6a. Cancelamento de campanha após o horário agendado: Sistema bloqueia a ação e exibe mensagem informando que o envio já foi iniciado/concluído.
6b. Turista com opt-out de marketing: Sistema não inclui o destinatário e registra a exclusão no histórico.
6c. Falha do serviço de envio: Sistema exibe status "Degradado" ou "Offline" no painel e marca os envios como "Falhou".
