### 3.23 Detalhes da Atrações/Gestão Financeira/Negociação Financeira/ - Administrador

**ID:** RF-023

**Módulo** : Gestão de Atrações &gt; Detalhes da Atração &gt; Gestão Financeira &gt; Negociação Financeira

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir ao Administrador e ao Parceiro Comercial visualizar as condições comerciais e as informações financeiras contratadas para a atração. A tela é acessada pelo menu Detalhes da Atração &gt; Gestão Financeira &gt; Negociação Financeira e reutiliza a mesma estrutura e os mesmos campos das telas de Condições Comerciais (RF-010) e de Informações Financeiras (RF-011), em modo somente leitura e restritos aos dados já vinculados ao contrato da atração.

Requisitos Detalhados

Referência às telas de Configurações Comerciais (RF-010 e RF-011)

As telas de Condições Comerciais e de Informações Financeiras exibidas em Negociação Financeira têm a mesma estrutura visual e os mesmos campos das telas do módulo Configurações Comerciais. Para a descrição dos campos, layout e validações, aplicar o definido em RF-010 (Condições Comerciais) e RF-011 (Informações Financeiras). A tabela abaixo resume apenas as diferenças de contexto, escopo e comportamento.

| Aspecto            | RF-010 / RF-011 (Configurações Comerciais)                        | RF-023 (Negociação Financeira em Detalhes da Atração)                                                        |
|--------------------|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Contexto de acesso | Menu global Configurações Comerciais                              | Detalhes da Atração > Gestão Financeira > Negociação Financeira                                              |
| Perfis             | Somente Administrador                                             | Administrador e Parceiro Comercial (apenas na atração vinculada)                                             |
| Escopo dos dados   | Catálogo global de condições e informações financeiras do sistema | Apenas as condições comerciais e as informações financeiras já vinculadas ao contrato da atração em contexto |
| Modo de operação   | Cadastro, edição, exclusão, cópia, ativar/inativar                | Somente leitura (visualização); não há botões Adicionar, Editar, Excluir nem barra de ações em massa         |
| Fonte dos dados    | Tabelas de condições e informações financeiras do sistema         | Dados do contrato da atração selecionada (já contratados)                                                    |

| ID        | Requisito                                                                                                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-023.01 | O sistema deve exibir o submenu Negociação Financeira sob Gestão Financeira (em Detalhes da Atração), com as opções Condições Comerciais e Informações Financeiras.                                                                  |
| RF-023.02 | Ao acessar Condições Comerciais neste contexto, o sistema deve exibir a tela com a mesma estrutura e os mesmos campos do RF-010, em modo somente leitura e restrita às condições vinculadas ao contrato da atração.                  |
| RF-023.03 | Ao acessar Informações Financeiras neste contexto, o sistema deve exibir a tela com a mesma estrutura e os mesmos campos do RF-011, em modo somente leitura e restrita às informações financeiras vinculadas ao contrato da atração. |
| RF-023.04 | O sistema não deve exibir botões de Adicionar, Editar, Excluir nem barra de ações em massa nas telas de Negociação Financeira; apenas visualização.                                                                                  |
| RF-023.05 | O sistema deve exibir título e subtítulo coerentes com o contexto (ex.: "Condições Comercial" / "Condições comerciais do contrato" e "Informação Financeira" / "Informações financeiras do contrato").                               |
| RF-023.06 | Parceiro Comercial deve acessar Negociação Financeira somente para atrações às quais está vinculado.                                                                                                                                 |
| RF-023.07 | Os dados exibidos devem ser os já cadastrados no contrato da atração (condições e informações financeiras contratadas).                                                                                                              |

Regras de Negócio

| ID        | Regra                                                                                                                                                                    |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-023.01 | As telas de Condições Comerciais e Informações Financeiras em Negociação Financeira são somente leitura; nenhum campo editável nem ação de cadastro, edição ou exclusão. |

Critérios de Aceitação

| ID        | Critério                                                                                                                   | Resultado Esperado                                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| CA-023.01 | Acessar Detalhes da Atração > Gestão Financeira > Negociação Financeira como Administrador ou Parceiro Comercial vinculado | Submenu exibe Condições Comerciais e Informações Financeiras; ao selecionar, abre tela com mesma estrutura e campos de RF-010 ou RF-011 |
| CA-023.02 | Verificar modo de operação em Condições Comerciais (Negociação Financeira)                                                 | Todos os campos em somente leitura; não há botões Adicionar, Editar ou Excluir                                                          |
| CA-023.03 | Verificar dados exibidos em Informações Financeiras (Negociação Financeira)                                                | Apenas as informações financeiras vinculadas ao contrato da atração em contexto                                                         |
| CA-023.04 | Parceiro Comercial acessar Negociação Financeira de atração não vinculada                                                  | Sistema impede o acesso ou não exibe a opção                                                                                            |

Protótipo/Wireframe

Figura  - WF-028 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Condições Comerciais

Figura  - WF-029 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Informações Financeiras

### 3.24 Detalhes da Atrações/Gestão Financeira/Resumo das Despesas - Administrador
