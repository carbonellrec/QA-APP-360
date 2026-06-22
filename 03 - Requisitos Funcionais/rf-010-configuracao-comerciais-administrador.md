### 3.10 Configuração Comerciais - Administrador

**ID:** RF-010

Módulo: Configurações Comerciais &gt; Condições Comerciais

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador cadastre, edite, visualize e gerencie as condições comerciais que serão vinculadas aos contratos. As condições comerciais definem as taxas aplicadas às transações da plataforma.

**Requisitos Detalhados**

**Estrutura da Tela**

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-010.01 | O sistema deve exibir título "Configurações Comerciais"                                             |
| RF-010.02 | O sistema deve exibir subtítulo "Gerencie as condições comerciais do sistema"                       |
| RF-010.03 | O sistema deve exibir abas principais: "Condições comerciais" e "Informações financeiras"           |
| RF-010.04 | O sistema deve exibir campo de busca                                                                |
| RF-010.05 | O sistema deve exibir botão "Filtro"                                                                |
| RF-010.06 | O sistema deve exibir botão "Adicionar condição"                                                    |
| RF-010.07 | O sistema deve exibir botão "Adicionar informação financeira" (redireciona para aba correspondente) |

**Sub-abas de Status**

| ID        | Requisito                                                     |
|-----------|---------------------------------------------------------------|
| RF-010.08 | O sistema deve exibir sub-abas: "Ativos", "Inativos", "Todos" |
| RF-010.09 | Por padrão, a aba "Ativos" deve estar selecionada             |

**Tabela de Condições Comerciais**

| Coluna                 | Descrição                                           | Ordenável   |
|------------------------|-----------------------------------------------------|-------------|
| Checkbox               | Seleção múltipla                                    | ❌           |
| ID                     | Identificador único da condição (auto-incrementado) | ✅           |
| Apelido                | Nome/identificador da condição                      | ✅           |
| Status                 | Ativo / Inativo (badge)                             | ✅           |
| Porcentagem/Valor      | Badge indicando tipo (Porcentagem ou Valor)         | ✅           |
| Valor                  | Valor da condição (% ou R$)                         | ✅           |
| Tx C.Crédito a Vista   | Taxa cartão crédito à vista                         | ✅           |
| Tx C.Crédito Parcelado | Taxa cartão crédito parcelado                       | ✅           |
| Tx Pix                 | Taxa PIX                                            | ✅           |
| Tx Antecipação         | Taxa de antecipação                                 | ✅           |
| Prazo pagamento        | Prazo em dias                                       | ✅           |
| Tx Internacional       | Taxa transação internacional                        | ✅           |

**Barra de Ações (ao selecionar registros)**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-010.10 | O sistema deve exibir barra de ações quando houver pelo menos 1 registro selecionado |
| RF-010.11 | O sistema deve exibir contador "Selecionados X"                                      |

**Ações Disponíveis:**

| Ação                  | Condição                                 | Descrição                                                                       |
|-----------------------|------------------------------------------|---------------------------------------------------------------------------------|
| Editar                | 1 selecionado + NÃO vinculado a contrato | Abre modal de edição                                                            |
| Copiar                | 1 selecionado                            | Abre modal preenchido para criar novo registro com as informações já peenchidas |
| Excluir               | Múltiplos + NÃO vinculados a contrato    | Exclui registros (soft delete)                                                  |
| Inativar selecionados | Múltiplos                                | Muda status para "Inativo"                                                      |

| ID        | Requisito                                                                                 |
|-----------|-------------------------------------------------------------------------------------------|
| RF-010.12 | Ao clicar em "Copiar", o sistema abre o modal de cadastro com todos os campos preenchidos |
| RF-010.13 | O usuário pode ajustar os valores e salvar como novo registro                             |

**Modal: Nova/Editar Condição Comercial**

| ID        | Requisito                                                                                               |
|-----------|---------------------------------------------------------------------------------------------------------|
| RF-010.14 | O sistema deve exibir modal com título "Nova Condição Comercial" ou "Editar Condição Comercial"         |
| RF-010.15 | O sistema deve exibir subtítulo "Preencha os campos obrigatórios para adicionar uma condição comercial" |
| RF-010.16 | O sistema deve exibir botões "Descartar" e "Salvar"                                                     |

**Campos do Formulário**

| Campo                    | Tipo            | Obrigatório   | Descrição                           |
|--------------------------|-----------------|---------------|-------------------------------------|
| ID da condição comercial | Somente leitura | -             | Gerado automaticamente após salvar  |
| Apelido                  | Texto           | ✅             | Nome identificador da condição      |
| Porcentagem/Valor        | Select          | ✅             | Opções: "Porcentagem" ou "Valor"    |
| Valor                    | Número          | ✅             | Exibe % se Porcentagem, R$ se Valor |
| Tx. C.Crédito a Vista    | %               | ✅             | Taxa cartão crédito à vista         |
| Tx. C.Crédito Parcelado  | %               | ✅             | Taxa cartão crédito parcelado       |
| Tx. Pix                  | %               | ✅             | Taxa PIX                            |
| Tx. Antecipação          | %               | ✅             | Taxa de antecipação                 |
| Tx. Internacional        | %               | ✅             | Taxa transação internacional        |
| Prazo para pagamento     | Número (dias)   | ✅             | Prazo em dias para pagamento        |
| Ativo                    | Toggle          | ✅             | Ativar/desativar a condição         |

**Comportamento do Campo Valor**

| ID        | Requisito                                                                           |
|-----------|-------------------------------------------------------------------------------------|
| RF-010.17 | Se Porcentagem/Valor = "Porcentagem", o campo Valor exibe máscara de percentual (%) |
| RF-010.18 | Se Porcentagem/Valor = "Valor", o campo Valor exibe máscara de moeda (R$)           |

**Alerta de Condição Vinculada**

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-010.19 | Se o usuário tentar editar uma condição vinculada a um contrato vigente, o sistema exibe alerta |
| RF-010.20 | Ao clicar em "Criar condição a partir desta", o sistema abre modal com dados preenchidos        |
| RF-010.21 | Ao clicar em "Selecionar outra condição", o sistema fecha o alerta                              |

**Busca e Filtros**

**Campo de Busca**

| ID        | Requisito                                      |
|-----------|------------------------------------------------|
| RF-010.22 | A busca deve pesquisar nos campos: ID, Apelido |

**Filtros Avançados**

| Filtro                   | Tipo   | Opções                |
|--------------------------|--------|-----------------------|
| Status                   | Select | Ativo, Inativo, Todos |
| Tipo (Porcentagem/Valor) | Select | Porcentagem, Valor    |
| Prazo pagamento          | Range  | De X a Y dias         |

**Paginação**

| ID        | Requisito                                                                                 |
|-----------|-------------------------------------------------------------------------------------------|
| RF-010.23 | O sistema deve carregar por padrão 10 registros por página                                |
| RF-010.24 | O sistema deve permitir alterar para exibir 10, 20, 50 ou 100 registros                   |
| RF-010.25 | O sistema deve exibir navegação: primeira página, anterior, "X a Y de Z", próxima, última |

**Regras de Negócio**

| ID        | Regra                                                                              |
|-----------|------------------------------------------------------------------------------------|
| RN-010.01 | O ID da condição é gerado automaticamente de forma incremental                     |
| RN-010.02 | Todos os campos do formulário são obrigatórios                                     |
| RN-010.03 | Condições comerciais são globais (não vinculadas a usuários específicos)           |
| RN-010.04 | Cada contrato pode ter apenas UMA condição comercial vinculada                     |
| RN-010.05 | Condições vinculadas a contratos vigentes (status Ativo) NÃO podem ser editadas    |
| RN-010.06 | Condições vinculadas a contratos vigentes exibem botão "Copiar" em vez de "Editar" |
| RN-010.07 | Ao copiar uma condição, o sistema cria um novo registro com novo ID                |
| RN-010.08 | Condições podem ser reutilizadas em múltiplos contratos                            |
| RN-010.09 | A exclusão é soft delete (marca como excluído no banco)                            |
| RN-010.10 | Condições vinculadas a contratos NÃO podem ser excluídas                           |
| RN-010.11 | Condições inativas não aparecem para seleção em novos contratos                    |

Critérios de Aceitação

**Visualização**

| ID        | Critério                         | Resultado Esperado                            |
|-----------|----------------------------------|-----------------------------------------------|
| CA-010.01 | Acessar Configurações Comerciais | Aba "Condições comerciais" exibida por padrão |
| CA-010.02 | Verificar tabela                 | Todas as colunas exibidas corretamente        |
| CA-010.03 | Selecionar aba "Inativos"        | Apenas condições inativas são exibidas        |

**Cadastro**

| ID        | Critério                               | Resultado Esperado                 |
|-----------|----------------------------------------|------------------------------------|
| CA-010.04 | Clicar em "Adicionar condição"         | Modal de cadastro abre vazio       |
| CA-010.05 | Preencher todos os campos e salvar     | Condição criada com status "Ativo" |
| CA-010.06 | Verificar ID após salvar               | ID gerado automaticamente          |
| CA-010.07 | Selecionar "Porcentagem" no campo tipo | Campo Valor exibe máscara %        |
| CA-010.08 | Selecionar "Valor" no campo tipo       | Campo Valor exibe máscara R$       |

**Edição e Cópia**

| ID        | Critério                                         | Resultado Esperado                                  |
|-----------|--------------------------------------------------|-----------------------------------------------------|
| CA-010.09 | Selecionar condição NÃO vinculada a contrato     | Botão "Editar" é exibido                            |
| CA-010.10 | Clicar em "Editar"                               | Modal abre com dados preenchidos                    |
| CA-010.11 | Selecionar condição vinculada a contrato vigente | Botão "Copiar" é exibido (não "Editar")             |
| CA-010.12 | Clicar em "Copiar"                               | Modal abre com dados preenchidos para novo registro |
| CA-010.13 | Salvar cópia                                     | Novo registro criado com novo ID                    |

**Alerta de Proteção**

| ID        | Critério                                        | Resultado Esperado                 |
|-----------|-------------------------------------------------|------------------------------------|
| CA-010.14 | Tentar editar condição vinculada via atalho/bug | Alerta "Condição em uso" é exibido |
| CA-010.15 | Clicar em "Criar condição a partir desta"       | Modal de cópia é aberto            |

**Exclusão**

| ID        | Critério                                     | Resultado Esperado                                                       |
|-----------|----------------------------------------------|--------------------------------------------------------------------------|
| CA-010.16 | Tentar excluir condição vinculada a contrato | Mensagem de erro: "Não é possível excluir condição vinculada a contrato" |
| CA-010.17 | Excluir condição não vinculada               | Condição removida (soft delete)                                          |

Protótipo/Wireframe

Figura  - WF-009 - Configurações Comerciais.png

Figura  - WF-010 - Configurações Comerciais/condição comercial

### 3.11 Informações Financeiras (Administrador)
