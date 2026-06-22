### 3.52 Central de Notificações - Administrador

**ID:** RF-052

Módulo: Central de Notificações

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** Módulo do Backoffice para gerenciar todo o sistema de comunicação com os turistas: criar e editar templates de notificação (e-mail e push), configurar regras de disparo automático por evento, criar campanhas de notificação segmentadas (broadcast manual ou agendado) e visualizar histórico e relatórios de envio. Respeita obrigatoriamente as preferências de opt-in configuradas pelo turista em RF-038 (LGPD).

Requisitos Detalhados

Estrutura Geral do Módulo

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.01 | O sistema deve exibir o módulo Central de Notificações acessível via menu lateral "Notificações"                                      |
| RF-052.02 | O módulo deve exibir sub-menu com 4 abas: Templates, Regras de Disparo, Campanhas, Histórico de Envios                               |
| RF-052.03 | O sistema deve exibir painel de resumo com: total de notificações enviadas no mês, taxa média de abertura de e-mail, taxa de entrega push — **somente leitura**, sem ações disponíveis para o ator |
| RF-052.04 | O sistema deve exibir indicador de status do serviço de envio (Operacional / Degradado / Offline) — **somente leitura**              |

Templates — Listagem

| ID        | Requisito                                                                                                                           |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.05 | O sistema deve exibir lista de templates com colunas: Nome, Tipo (E-mail / Push / Ambos), Evento Associado, Status, Última Edição  |
| RF-052.06 | O sistema deve exibir botão "Novo Template" que abre tela de criação                                                               |
| RF-052.07 | O sistema deve exibir botão "Editar" por template                                                                                  |
| RF-052.08 | O sistema deve exibir botão "Duplicar" que cria cópia do template com status Inativo por padrão                                   |
| RF-052.09 | O sistema deve exibir toggle "Ativar/Inativar" por template                                                                        |
| RF-052.10 | O sistema deve permitir busca de templates por nome e filtro por Tipo e Status                                                     |

Templates — Editor de E-mail

| ID        | Requisito                                                                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.11 | O editor de template de e-mail deve exibir campo "Assunto" com suporte a variáveis dinâmicas (ex.: `{{nome_turista}}`, `{{nome_atracao}}`)        |
| RF-052.12 | O editor deve exibir corpo HTML via WYSIWYG com lista de variáveis disponíveis para o tipo de evento selecionado                                  |
| RF-052.13 | O sistema deve exibir botão "Pré-visualizar" com visualizações Desktop e Mobile do e-mail renderizado                                             |
| RF-052.14 | O sistema deve exibir botão "Enviar e-mail de teste" que envia o template para um endereço informado pelo Admin                                   |
| RF-052.15 | O sistema deve validar as variáveis do template ao salvar, exibindo erro se houver variável não reconhecida (ex.: `{{variavel_invalida}}`)        |
| RF-052.16 | O sistema deve exibir botão "Salvar" (mantém status atual) e "Salvar e Ativar" (ativa o template)                                                 |

Templates — Editor de Push

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.17 | O editor de template push deve exibir campo "Título" com contador de caracteres (máx 50)                                             |
| RF-052.18 | O editor deve exibir campo "Corpo da mensagem" com contador de caracteres (máx 150)                                                  |
| RF-052.19 | O editor deve exibir campo "Link de destino" (URL que abre ao clicar na notificação)                                                 |
| RF-052.20 | O editor deve exibir campo de upload de ícone/imagem opcional (JPEG/PNG, máx 512 KB)                                                 |
| RF-052.21 | O sistema deve exibir pré-visualização do push notification conforme preenchimento dos campos                                        |

Regras de Disparo Automático

| ID        | Requisito                                                                                                                                    |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.22 | O sistema deve exibir lista de regras de disparo por tipo de evento com colunas: Evento, Canal, Template, Delay, Opt-in, Status            |
| RF-052.23 | Para cada tipo de evento, o Admin deve poder configurar: Canal (E-mail / Push / Ambos), Template associado, Delay (Imediato / X horas / X dias), Condição de opt-in |
| RF-052.24 | A condição de opt-in deve ter duas opções: "Obrigatório" (disponível **exclusivamente para eventos Transacionais** — envia independente de preferências) e "Respeita opt-in" (verifica RF-038); para eventos de Marketing/Opt-in, a opção "Obrigatório" deve estar **desabilitada/bloqueada** na interface, sendo "Respeita opt-in" a única opção disponível |
| RF-052.25 | A regra especial "Lembrete de Visita" deve exibir campo adicional para configurar quantos dias antes do evento enviar a notificação        |
| RF-052.26 | O sistema deve exibir toggle Ativar/Desativar por regra individualmente                                                                     |
| RF-052.27 | Regra desativada não dispara notificações mesmo que o evento ocorra                                                                         |

Campanhas — Criação e Gestão

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.28 | O sistema deve exibir botão "Nova Campanha" que abre formulário de criação                                                            |
| RF-052.29 | O formulário de campanha deve exibir campos: Nome, Tipo (E-mail / Push), Template (dropdown de templates ativos do tipo selecionado)  |
| RF-052.30 | O formulário deve exibir seleção de segmentação do público-alvo: Todos os turistas / Por categoria de preferência / Por cidade / Por histórico de compra / **Turistas com opt-in ativo para marketing** |
| RF-052.31 | O sistema deve exibir estimativa de alcance (quantidade de turistas) atualizada ao alterar a segmentação                              |
| RF-052.32 | O formulário deve exibir campos de Data/Hora de envio: Imediato ou Agendado (data e hora futuras)                                    |
| RF-052.33 | O sistema deve bloquear a criação de campanha com template inativo, exibindo mensagem de erro                                         |
| RF-052.34 | O sistema deve exibir lista de campanhas com colunas: Nome, Tipo, Status (Rascunho/Agendada/Enviada/Cancelada), Data Envio, Enviados, Taxa Abertura |
| RF-052.35 | O sistema deve exibir botão "Cancelar" para campanhas com status "Agendada" (disponível somente antes do horário de envio)           |
| RF-052.36 | O formulário de criação de campanha deve exibir botão **"Salvar como Rascunho"**, permitindo preservar a configuração sem agendar ou enviar; rascunhos podem ser editados e reaproveitados posteriormente |
| RF-052.37 | O sistema deve exibir botão **"Duplicar"** por campanha, criando cópia com status Rascunho por padrão; campanhas com status "Cancelada" ou "Enviada" também podem ser duplicadas |

Histórico de Envios

| ID        | Requisito                                                                                                                               |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------|
| RF-052.38 | O sistema deve exibir log de todas as notificações enviadas (transacionais e campanhas) com colunas: Data/Hora, Turista, Evento/Campanha, Canal, Status |
| RF-052.39 | Os status possíveis de cada envio são: Enviado, Aberto, Falhou, Bounced                                                                |
| RF-052.40 | O sistema deve exibir filtros: Canal, Status, Evento/Campanha, Período                                                                  |
| RF-052.41 | O sistema deve exibir taxa de abertura por campanha de e-mail e taxa de entrega por campanha push                                      |
| RF-052.42 | O sistema deve exibir botão "Exportar CSV" para o histórico conforme filtros aplicados                                                  |

Tipos de Evento

| Evento                       | Categoria        | Opt-out pelo Turista | Condição de Opt-in Disponível |
|------------------------------|------------------|----------------------|-------------------------------|
| Compra Confirmada            | Transacional     | Não permitido        | Obrigatório ou Respeita opt-in |
| Reembolso Aprovado           | Transacional     | Não permitido        | Obrigatório ou Respeita opt-in |
| Reembolso Rejeitado          | Transacional     | Não permitido        | Obrigatório ou Respeita opt-in |
| Senha Redefinida             | Transacional     | Não permitido        | Obrigatório ou Respeita opt-in |
| Lembrete de Visita           | Opt-in           | Permitido (RF-038)   | Respeita opt-in (único disponível) |
| Promoção / Oferta Especial   | Marketing/Opt-in | Permitido (RF-038)   | Respeita opt-in (único disponível) |
| Nova Atração Disponível      | Marketing/Opt-in | Permitido (RF-038)   | Respeita opt-in (único disponível) |
| Cupom de Desconto            | Marketing/Opt-in | Permitido (RF-038)   | Respeita opt-in (único disponível) |

Variáveis Disponíveis por Evento (exemplos)

| Variável             | Disponível em                               |
|----------------------|---------------------------------------------|
| `{{nome_turista}}`   | Todos os eventos                            |
| `{{nome_atracao}}`   | Compra, Reembolso, Lembrete, Promoção       |
| `{{data_visita}}`    | Lembrete de Visita                          |
| `{{valor_reembolso}}`| Reembolso Aprovado / Rejeitado              |
| `{{codigo_cupom}}`   | Cupom de Desconto                           |
| `{{link_ingresso}}`  | Compra Confirmada                           |
| `{{motivo_rejeicao}}`| Reembolso Rejeitado                         |

Regras de Negócio

| ID        | Regra                                                                                                                                           |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-052.01 | Apenas o perfil **Administrador** tem acesso a este módulo                                                                                      |
| RN-052.02 | Notificações transacionais (Compra, Reembolso, Senha) **não podem ser bloqueadas** pelo turista; são sempre enviadas                            |
| RN-052.03 | Notificações de marketing respeitam obrigatoriamente as preferências de opt-in do turista (RF-038 / LGPD); turista que optou por não receber não receberá; **a configuração de regra de disparo não pode sobrepor esta restrição para eventos de Marketing/Opt-in** |
| RN-052.04 | Template inativo **não pode** ser associado a nova regra de disparo ou campanha                                                                 |
| RN-052.05 | Variáveis de template são validadas ao salvar; variável não reconhecida impede salvamento com mensagem de erro                                  |
| RN-052.06 | Campanhas são enviadas apenas para turistas com **e-mail verificado**                                                                           |
| RN-052.07 | Push notifications exigem **consentimento explícito** do turista (além do opt-in da categoria de notificação)                                   |
| RN-052.08 | SLA de entrega: e-mail transacional ≤ **2 minutos**, push ≤ **1 minuto**, e-mail marketing ≤ **15 minutos** após o disparo                     |
| RN-052.09 | Histórico de envios é retido por **12 meses**; registros mais antigos são arquivados automaticamente                                            |
| RN-052.10 | Campanha agendada pode ser **cancelada somente antes** do horário de envio programado                                                           |
| RN-052.11 | Duplicar template cria cópia com status **Inativo** por padrão, evitando uso acidental antes de revisão                                        |
| RN-052.12 | Excluir template não exclui o histórico de envios vinculado; o template aparece como "[Excluído]" no histórico de envios; templates excluídos **não podem ser reaproveitados** — para reutilizar o conteúdo, deve-se duplicar o template antes de excluí-lo |
| RN-052.13 | **[NOVO]** A condição "Obrigatório" está disponível **exclusivamente para eventos da categoria Transacional**; eventos de Marketing/Opt-in sempre respeitam as preferências do turista (RF-038), sem exceção; nenhuma configuração de regra de disparo pode sobrepor esta restrição |

Critérios de Aceitação

| ID        | Critério                                                                                      | Resultado Esperado                                                                                       |
|-----------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| CA-052.01 | Acessar Central de Notificações como Administrador                                            | Sub-menu com 4 abas exibido; painel de resumo com métricas do mês visível; painel e indicador de status são somente leitura |
| CA-052.02 | Criar template de e-mail com variável válida `{{nome_turista}}`                               | Template salvo; variável reconhecida; sem erros                                                          |
| CA-052.03 | Criar template de e-mail com variável inválida `{{campo_inexistente}}`                        | Mensagem de erro: variável não reconhecida; template não salvo                                           |
| CA-052.04 | Clicar em "Enviar e-mail de teste" informando endereço válido                                 | E-mail de teste recebido no endereço informado com o layout do template                                  |
| CA-052.05 | Criar template push e digitar título com 55 caracteres                                        | Campo bloqueado ao atingir 50 caracteres; contador exibe valor máximo                                    |
| CA-052.06 | Inativar um template ativo                                                                    | Template não aparece no dropdown de seleção ao criar nova regra ou campanha                              |
| CA-052.07 | Tentar criar campanha com template inativo selecionado                                        | Mensagem de erro: "Template inativo não pode ser usado em campanhas"                                     |
| CA-052.08 | Configurar regra de disparo para "Lembrete de Visita" com 3 dias de antecedência              | Regra salva; notificações disparadas 3 dias antes da data do evento para turistas opt-in                 |
| CA-052.09 | Desativar uma regra de disparo                                                                | Evento ocorre sem disparar notificação correspondente                                                    |
| CA-052.10 | Criar campanha agendada para data futura                                                      | Campanha criada com status "Agendada"; botão "Cancelar" disponível                                       |
| CA-052.11 | Cancelar campanha agendada antes do horário de envio                                          | Status muda para "Cancelada"; nenhuma notificação enviada                                                |
| CA-052.12 | Verificar histórico de envios com filtro por canal "Push"                                     | Lista filtrada exibindo apenas notificações push                                                         |
| CA-052.13 | Exportar histórico de envios para CSV                                                         | Arquivo CSV gerado com os registros conforme filtros aplicados                                           |
| CA-052.14 | Verificar que turista com opt-out de marketing não recebe campanha de promoção                | Campanha enviada; turista com opt-out não consta nos destinatários; histórico confirma não envio         |
| CA-052.15 | Duplicar template existente                                                                   | Cópia criada com nome "[Nome original] (cópia)" e status Inativo                                        |
| CA-052.16 | **[NOVO]** Excluir template e verificar histórico de envios que o utilizou                   | Template aparece como "[Excluído]" no histórico; registros de envio preservados; template não aparece no dropdown de seleção |
| CA-052.17 | **[NOVO]** Tentar configurar condição "Obrigatório" em regra de disparo vinculada a evento de Marketing/Opt-in (ex.: "Promoção / Oferta Especial") | Opção "Obrigatório" desabilitada/bloqueada na interface; apenas "Respeita opt-in" disponível para seleção |
| CA-052.18 | **[NOVO]** Criar campanha e clicar em "Salvar como Rascunho" sem definir data de envio       | Campanha salva com status "Rascunho"; pode ser editada e reaproveitada posteriormente                    |
| CA-052.19 | **[NOVO]** Duplicar campanha com status "Enviada"                                             | Cópia criada com status "Rascunho"; todos os campos copiados; campanha original preservada               |
| CA-052.20 | **[NOVO]** Segmentar campanha por "Turistas com opt-in ativo para marketing"                  | Estimativa de alcance exibe apenas turistas com opt-in de marketing ativo; campanha enviada somente a esse segmento |

Protótipo/Wireframe

Figura - WF-056 - Central de Notificações.png (a definir)
