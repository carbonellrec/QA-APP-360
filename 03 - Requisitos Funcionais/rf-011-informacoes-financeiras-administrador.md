### 3.11 Informações Financeiras (Administrador)

**ID:** RF-011

Módulo:	Configurações Comerciais &gt; Informações Financeiras

Perfis com Acesso:	Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador cadastre, edite, visualize e gerencie as informações financeiras que serão vinculadas aos contratos. As informações financeiras definem os parâmetros de saque e taxas de transferência para os parceiros.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                |
|-----------|------------------------------------------------------------------------------------------|
| RF-011.01 | O sistema deve exibir a aba "Informações financeiras" no módulo Configurações Comerciais |
| RF-011.02 | O sistema deve exibir botão "Adicionar informação financeira"                            |
| RF-011.03 | O sistema deve exibir sub-abas: "Ativos", "Inativos", "Todos"                            |

Tabela de Informações Financeiras

| Coluna           | Descrição                               | Ordenável   |
|------------------|-----------------------------------------|-------------|
| Checkbox         | Seleção múltipla                        | ❌           |
| ID               | Identificador único (auto-incrementado) | ✅           |
| Apelido          | Nome/identificador                      | ✅           |
| Status           | Ativo / Inativo (badge)                 | ✅           |
| Liberado saque   | Sim / Não                               | ✅           |
| % Liberado saque | Percentual para saque                   | ✅           |
| Valor máx. saque | Valor máximo                            | ✅           |
| Tempo mín. saque | Dias                                    | ✅           |
| Desconto PIX     | Sim/Não + Valor                         | ✅           |
| Desconto TED     | Sim/Não + Valor                         | ✅           |

Barra de Ações (ao selecionar registros)

| Ação                  | Condição                                          | Descrição                             |
|-----------------------|---------------------------------------------------|---------------------------------------|
| Editar                | 1 selecionado + NÃO vinculado a contrato assinado | Abre modal de edição                  |
| Copiar                | 1 selecionado                                     | Abre modal preenchido para criar novo |
| Excluir               | Múltiplos + NÃO vinculados                        | Exclui (soft delete)                  |
| Inativar selecionados | Múltiplos                                         | Muda status para "Inativo"            |

Modal: Nova/Editar Informação Financeira

| ID        | Requisito                                                                                                  |
|-----------|------------------------------------------------------------------------------------------------------------|
| RF-011.04 | O sistema deve exibir modal com título "Nova Informação Financeira"                                        |
| RF-011.05 | O sistema deve exibir subtítulo "Preencha os campos obrigatórios para adicionar uma informação financeira" |
| RF-011.06 | O sistema deve exibir botões "Descartar" e "Salvar"                                                        |

Campos do Formulário

| Campo                          | Tipo             | Obrigatório   | Descrição                    |
|--------------------------------|------------------|---------------|------------------------------|
| ID da informação financeira    | Somente leitura  | -             | Gerado automaticamente       |
| Apelido                        | Texto            | ✅             | Nome identificador           |
| Liberado saque                 | Select (Sim/Não) | ✅             | Permite saque dos valores    |
| Percentual liberado para saque | %                | ✅             | Percentual disponível        |
| Valor liberado para saque      | Moeda (R$)       | ✅             | Valor máximo por saque       |
| Tempo mínimo para saque        | Número (dias)    | ✅             | Dias após venda para liberar |
| Descontar valor por PIX        | Select (Sim/Não) | ✅             | Aplicar desconto PIX         |
| Desconto PIX                   | Moeda (R$)       | Condicional   | Visível apenas se PIX = Sim  |
| Descontar valor por TED        | Select (Sim/Não) | ✅             | Aplicar desconto TED         |
| Desconto TED                   | Moeda (R$)       | Condicional   | Visível apenas se TED = Sim  |
| Ativo                          | Toggle           | ✅             | Ativar/desativar             |

Campos Condicionais

| ID        | Requisito                                                                           |
|-----------|-------------------------------------------------------------------------------------|
| RF-011.07 | O campo "Desconto PIX" só é exibido se "Descontar valor por PIX" = Sim              |
| RF-011.08 | O campo "Desconto TED" só é exibido se "Descontar valor por TED" = Sim              |
| RF-011.09 | Se o toggle mudar para "Não", o campo de desconto correspondente é ocultado e limpo |

Alerta de Informação Vinculada

| ID        | Requisito                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------|
| RF-011.10 | Se o usuário tentar editar uma informação vinculada a um contrato assinado, o sistema exibe alerta                                     |
| RF-011.11 | O alerta deve conter a mensagem “Esta informação financeira não pode ser editada pois já está sendo utilizada em um contrato assinado” |
| RF-011.12 | O sistema deve dar a opção de “Criar informação a partir desta” ou “Selecionar outra informação financeira”.                           |

Regras de Negócio

| ID        | Regra                                                                              |
|-----------|------------------------------------------------------------------------------------|
| RN-011.01 | O ID é gerado automaticamente de forma incremental                                 |
| RN-011.02 | Todos os campos (exceto condicionais) são obrigatórios                             |
| RN-011.03 | Informações financeiras são globais (não vinculadas a usuários)                    |
| RN-011.04 | Um contrato pode ter uma informações financeiras vinculada                         |
| RN-011.05 | Informações vinculadas a contratos assinados (status Ativo) NÃO podem ser editadas |
| RN-011.06 | Informações vinculadas exibem botão "Copiar" em vez de "Editar"                    |
| RN-011.07 | Ao copiar, o sistema cria um novo registro com novo ID                             |
| RN-011.08 | Informações podem ser reutilizadas em múltiplos contratos                          |
| RN-011.09 | A exclusão é soft delete                                                           |
| RN-011.10 | Informações vinculadas a contratos NÃO podem ser excluídas                         |
| RN-011.11 | Informações inativas não aparecem para seleção em novos contratos                  |
| RN-011.12 | O campo "Desconto PIX" só é obrigatório se "Descontar valor por PIX" = Sim         |
| RN-011.13 | O campo "Desconto TED" só é obrigatório se "Descontar valor por TED" = Sim         |

Critérios de Aceitação

Visualização

| ID        | Critério                                | Resultado Esperado                          |
|-----------|-----------------------------------------|---------------------------------------------|
| CA-011.01 | Clicar na aba "Informações financeiras" | Tabela de informações financeiras é exibida |
| CA-011.02 | Verificar colunas                       | Todas as colunas específicas são exibidas   |

Cadastro

| ID        | Critério                                    | Resultado Esperado                   |
|-----------|---------------------------------------------|--------------------------------------|
| CA-011.03 | Clicar em "Adicionar informação financeira" | Modal de cadastro abre vazio         |
| CA-011.04 | Selecionar "Descontar valor por PIX" = Sim  | Campo "Desconto PIX" aparece         |
| CA-011.05 | Selecionar "Descontar valor por PIX" = Não  | Campo "Desconto PIX" desaparece      |
| CA-011.06 | Selecionar "Descontar valor por TED" = Sim  | Campo "Desconto TED" aparece         |
| CA-011.07 | Preencher todos os campos e salvar          | Informação criada com status "Ativo" |

Edição e Cópia

| ID        | Critério                                                | Resultado Esperado                       |
|-----------|---------------------------------------------------------|------------------------------------------|
| CA-011.08 | Selecionar informação NÃO vinculada a contrato assinado | Botão "Editar" é exibido                 |
| CA-011.09 | Selecionar informação vinculada a contrato assinado     | Botão "Copiar" é exibido                 |
| CA-011.10 | Clicar em "Copiar"                                      | Modal abre preenchido para novo registro |

Proteção

| ID        | Critério                                               | Resultado Esperado                   |
|-----------|--------------------------------------------------------|--------------------------------------|
| CA-011.11 | Tentar editar informação vinculada a contrato assinado | Alerta "Informação em uso" é exibido |
| CA-011.12 | Tentar excluir informação vinculada                    | Mensagem de erro é exibida           |

**Protótipo/Wireframe**

Figura  - WF-011 - Configurações Comerciais/informação financeira.png

### 3.12 Tela de Gestão de Atrações - Administrador
