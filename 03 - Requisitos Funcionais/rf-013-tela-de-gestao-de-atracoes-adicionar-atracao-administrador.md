### 3.13 Tela de Gestão de Atrações/Adicionar Atração - Administrador

**ID:** RF-013

Módulo: Gestão de Atrações &gt; Cadastro/Edição

Perfis com Acesso: Administrador e Parceiro Comercial

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador cadastre novas atrações ou edite atrações existentes através de um modal de 3 etapas. O mesmo modal é utilizado para as ações: Novo, Editar e Visualizar. O cadastro permite salvar como rascunho a qualquer momento e retomar posteriormente.

**Requisitos Detalhados**

**Estrutura Geral do modal**

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-013.01 | O sistema deve exibir o cadastro em formato steps com 3 etapas                         |
| RF-013.02 | O sistema deve exibir o título dinâmico: "Nova Atração X/3" ou "Editar Atração X/3"    |
| RF-013.03 | O sistema deve exibir subtítulo contextual para cada etapa                             |
| RF-013.04 | O sistema deve permitir navegação entre etapas através dos botões "Voltar" e "Próximo" |
| RF-013.05 | O sistema deve exibir indicador visual de progresso das etapas                         |

**Botões de Ação (Todas as Etapas)**

| Botão           | Ação                                                                  |
|-----------------|-----------------------------------------------------------------------|
| Descartar       | Descarta TODAS as etapas e fecha o modal (exibe confirmação)          |
| Salvar Rascunho | Salva o progresso atual com status "Rascunho"                         |
| Voltar          | Retorna para a etapa anterior (não aparece na etapa 1)                |
| Próximo         | Avança para a próxima etapa (valida campos obrigatórios)              |
| Finalizar       | Salva a atração com status "Pendente de Contrato" (apenas na etapa 3) |

**Modos de Exibição**

| Modo       | Comportamento                                                           |
|------------|-------------------------------------------------------------------------|
| Novo       | Campos vazios, prontos para preenchimento                               |
| Editar     | Campos preenchidos com dados existentes, todos editáveis                |
| Visualizar | Campos preenchidos e desabilitados, botão "Habilitar Edição" disponível |

**ETAPA 1/3 - Dados da Atração**

Subtítulo: "Insira os dados da atração"

**Foto de Capa**

| ID        | Requisito                                                       |
|-----------|-----------------------------------------------------------------|
| RF-013.06 | O sistema deve exibir área para upload de Foto de Capa          |
| RF-013.07 | O sistema deve aceitar formatos: PNG, JPEG                      |
| RF-013.08 | O sistema deve limitar o tamanho máximo em 15MB                 |
| RF-013.09 | O sistema deve exibir botões "Carregar nova foto" e "Apagar"    |
| RF-013.10 | O botão "Apagar" remove a foto atual e exibe placeholder padrão |

**Parceiro Comercial**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-013.11 | O sistema deve exibir campo "Parceiro Comercial" (obrigatório) tipo select com busca |
| RF-013.12 | O campo deve listar apenas Parceiros Comerciais com status "Ativo"                   |
| RF-013.13 | O campo deve permitir pesquisa por nome ou ID do parceiro                            |

**Dados do Evento**

| ID        | Campo                 | Tipo              | Obrigatório   | Observação                                         |
|-----------|-----------------------|-------------------|---------------|----------------------------------------------------|
| RF-013.14 | Nome da Atração       | Texto             | ✅ Sim         | Máx. 150 caracteres                                |
| RF-013.15 | Local                 | Texto             | ✅ Sim         | Campo livre para digitação                         |
| RF-013.16 | CEP                   | Texto com máscara | ✅ Sim         | Formato: 00000-000                                 |
| RF-013.17 | Estado                | Select            | ✅ Sim         | Lista de UFs brasileiras                           |
| RF-013.18 | Cidade                | Texto             | ✅ Sim         | Pode ser preenchido automaticamente via CEP        |
| RF-013.19 | Endereço              | Texto             | ✅ Sim         | Logradouro completo                                |
| RF-013.20 | Número                | Texto             | ✅ Sim         | -                                                  |
| RF-013.21 | Complemento           | Texto             | ❌ Não         | -                                                  |
| RF-013.22 | Classificação Etária  | Select            | ✅ Sim         | Livre, 10 anos, 12 anos, 14 anos, 16 anos, 18 anos |
| RF-013.23 | Capacidade de Público | Numérico          | ✅ Sim         | Quantidade máxima de pessoas                       |
| RF-013.24 | Menor Acompanhado     | Select            | ✅ Sim         | Sim / Não                                          |

**Sessões do Evento**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-013.25 | O sistema deve permitir cadastrar múltiplas sessões para a atração                   |
| RF-013.26 | Cada sessão deve conter: Data  **,**  Horário de Início  **,**  Abertura dos Portões |
| RF-013.27 | O sistema deve exibir botão "Adicionar Sessão" para incluir novas datas              |
| RF-013.28 | O sistema deve permitir remover sessões adicionadas                                  |
| RF-013.29 | Deve haver pelo menos 1 sessão cadastrada (obrigatório)                              |

| Campo                | Tipo        | Formato    |
|----------------------|-------------|------------|
| Data                 | Date picker | DD/MM/YYYY |
| Horário de Início    | Time picker | HH:MM      |
| Abertura dos Portões | Time picker | HH:MM      |

**Informações Adicionais**

| ID        | Campo                   | Tipo   | Obrigatório   |
|-----------|-------------------------|--------|---------------|
| RF-013.30 | Espaço Coberto          | Select | ✅ Sim         |
| RF-013.31 | Acesso para Deficientes | Select | ✅ Sim         |
| RF-013.32 | Estacionamento no Local | Select | ✅ Sim         |

**ETAPA 2/3 - Dados Bancários e Materiais**

Subtítulo: "Insira os dados bancários"

**Dados Bancários do Parceiro**

| ID        | Requisito                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------|
| RF-013.33 | O sistema deve exibir campo "Utilizar dados bancários do parceiro?" (Sim/Não)                             |
| RF-013.34 | Se "Sim": preencher automaticamente os campos bancários com dados do Parceiro e deixá-los somente leitura |
| RF-013.35 | Se "Não": campos bancários ficam editáveis para preenchimento manual                                      |

**Dados Bancários para Depósito**

| ID        | Campo                        | Tipo              | Obrigatório   |
|-----------|------------------------------|-------------------|---------------|
| RF-013.36 | Banco                        | Select            | ✅ Sim         |
| RF-013.37 | Agência                      | Texto             | ✅ Sim         |
| RF-013.38 | Conta Corrente               | Texto             | ✅ Sim         |
| RF-013.39 | Beneficiário                 | Texto             | ✅ Sim         |
| RF-013.40 | CPF/CNPJ                     | Texto com máscara | ✅ Sim         |
| RF-013.41 | E-mail para envio de borderô | E-mail            | ✅ Sim         |

**Negociação**

| ID        | Requisito                                                         |
|-----------|-------------------------------------------------------------------|
| RF-013.42 | O sistema deve exibir campo "Negociação" (área de texto)          |
| RF-013.43 | O campo deve ter placeholder: "Negociação de formas de pagamento" |
| RF-013.44 | Campo opcional para registrar condições especiais negociadas      |

**Materiais para Divulgação**

| ID        | Requisito                                                                                 |
|-----------|-------------------------------------------------------------------------------------------|
| RF-013.45 | O sistema deve exibir seção "Materiais necessários para a criação e divulgação do evento" |

| Campo                         | Dimensão     | Formato   | Obrigatório   |
|-------------------------------|--------------|-----------|---------------|
| Home (capa do evento no site) | 1080×1080 px | PNG, JPEG | ❌ Não         |
| Imagem da atração             | 1170×430 px  | PNG, JPEG | ❌ Não         |
| Fundo                         | 1920×1080 px | PNG, JPEG | ❌ Não         |

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-013.46 | Cada campo de imagem deve exibir botão "Escolher arquivo" e indicador "Nenhum arquivo escolhido" |
| RF-013.47 | Após upload, exibir nome do arquivo e opção de remover                                           |

**Link de Vídeo e Release**

| ID        | Campo                     | Tipo          | Obrigatório   |
|-----------|---------------------------|---------------|---------------|
| RF-013.48 | Link de vídeo promocional | URL           | ❌ Não         |
| RF-013.49 | Release da atração        | Área de texto | ❌ Não         |

**ETAPA 3/3 - Dados do Ingresso**

Subtítulo: "Insira os dados do ingresso"

**Configuração de Ingressos**

| ID        | Requisito                                                                     |
|-----------|-------------------------------------------------------------------------------|
| RF-013.50 | O sistema deve permitir configurar múltiplos tipos de ingresso para a atração |
| RF-013.51 | Cada tipo de ingresso é associado a uma categoria                             |

**Categoria de Ingresso**

| ID        | Requisito                                                                          |
|-----------|------------------------------------------------------------------------------------|
| RF-013.52 | O sistema deve exibir campo "Categoria" tipo multi-select                          |
| RF-013.53 | O campo deve listar categorias já cadastradas para esta atração                    |
| RF-013.54 | O sistema deve exibir botão "Adicionar categoria"                                  |
| RF-013.55 | Ao clicar em "Adicionar categoria", abrir modal de criação de categoria (RF-015)   |
| RF-013.56 | Após salvar nova categoria, ela deve aparecer automaticamente selecionada no campo |

**Campos por Categoria de Ingresso**

| ID        | Campo                   | Tipo       | Obrigatório   | Observação                                       |
|-----------|-------------------------|------------|---------------|--------------------------------------------------|
| RF-013.57 | Status                  | Select     | ✅ Sim         | Ativo / Inativo                                  |
| RF-013.58 | Valor                   | Moeda (R$) | ✅ Sim         | Formato: R$ 0,00                                 |
| RF-013.59 | Quantidade              | Numérico   | ✅ Sim         | Quantidade disponível para venda                 |
| RF-013.60 | Lote                    | Numérico   | ❌ Não         | Identificador do lote (001, 002...)              |
| RF-013.61 | Mensagem customizada    | Texto      | ❌ Não         | Texto que aparece no ingresso do turista         |
| RF-013.62 | Expiração do pedido (h) | Numérico   | ✅ Sim         | Horas para cancelamento automático sem pagamento |

**Lotes de Venda**

| ID        | Requisito                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------|
| RF-013.63 | O campo "Lote" permite controlar vendas por lotes com preços diferenciados                             |
| RF-013.64 | Quando um lote esgota a quantidade, a venda passa automaticamente para o próximo lote (se configurado) |

**Regras de Negócio**

| #         | Regra                                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------|
| RN-013.01 | Rascunho: Ao salvar como rascunho, não é necessário preencher campos obrigatórios                                                            |
| RN-013.02 | Finalizar: Ao clicar em "Finalizar", todos os campos obrigatórios devem estar preenchidos                                                    |
| RN-013.03 | Status Inicial: Atração finalizada recebe status "Pendente de Contrato"                                                                      |
| RN-013.04 | Visibilidade: Atrações com status "Pendente de Contrato" ou "Rascunho" NÃO são visíveis no portal público                                    |
| RN-013.05 | Ativação Automática: Quando o contrato vinculado for assinado, a atração muda automaticamente para status "Ativo"                            |
| RN-013.06 | Categorias Vinculadas: Categorias de ingresso são exclusivas da atração (não são globais)                                                    |
| RN-013.07 | Expiração de Pedido: Pedidos não pagos dentro do tempo de expiração são cancelados automaticamente pelo sistema                              |
| RN-013.08 | Continuidade: Ao salvar como rascunho e retornar posteriormente, o modal deve abrir na última etapa preenchida                               |
| RN-013.09 | Descartar: Ao clicar em "Descartar", exibir confirmação: "Tem certeza que deseja descartar? Todas as informações não salvas serão perdidas." |
| RN-013.10 | Validação de CEP: Ao preencher o CEP, buscar automaticamente Estado, Cidade e Endereço (integração com API de CEP)                           |
| RN-013.11 | Dados Bancários: Se "Utilizar dados bancários do parceiro" = Sim, os campos devem ser preenchidos e bloqueados                               |
| RN-013.12 | Mínimo de Sessão: Pelo menos 1 sessão deve ser cadastrada para finalizar a atração                                                           |
| RN-013.13 | Mínimo de Ingresso: Pelo menos 1 categoria de ingresso deve ser configurada para finalizar a atração                                         |

Critérios de Aceitação

| #         | Critério                                                                                                                                                       |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-013.01 | Dado que o Admin está na etapa 1 e clica em "Salvar Rascunho", quando salva, então a atração deve ser criada com status "Rascunho"                             |
| CA-013.02 | Dado que o Admin preenche todos os campos obrigatórios e clica em "Finalizar", quando salva, então a atração deve ser criada com status "Pendente de Contrato" |
| CA-013.03 | Dado que o Admin seleciona "Utilizar dados bancários do parceiro = Sim", quando os campos carregam, então devem estar preenchidos e desabilitados              |
| CA-013.04 | Dado que o Admin adiciona uma nova categoria na etapa 3, quando salva a categoria, então ela deve aparecer selecionada automaticamente                         |
| CA-013.05 | Dado que o Admin clica em "Descartar", quando confirma, então o modal deve fechar e nenhum dado deve ser salvo                                                 |
| CA-013.06 | Dado que uma atração tem pedido não pago há mais de 48h (expiração configurada), quando o sistema processa, então o pedido deve ser cancelado automaticamente  |
| CA-013.07 | Dado que o Admin está na etapa 3 e clica em "Voltar", quando a navegação ocorre, então deve exibir a etapa 2 com os dados já preenchidos                       |

Protótipo/Wireframe

Figura  - WF-013 - Gestão de atrações/Adicionar Atração 1

Figura  WF-014 - Gestão de atrações/Adicionar Atração 2

Figura  - WF-015 - Gestão de atrações/Adicionar Atração 3

### 3.14 Detalhes da Atrações/Categorias – Administrador
