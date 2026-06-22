### 3.22 Detalhes da Atrações/Gestão Financeira/Relatórios da Atração- Administrador

**ID:** RF-022

**Módulo** : Gestão de Atrações &gt; Detalhes da Atração &gt; Gestão Financeira &gt; Relatórios da Atração

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade** : Alta (Essencial)

**Descrição** : O sistema deve permitir aos usuários Administrador e Parceiro Comercial a emissão de relatórios gerenciais da atração. A tela é acessada pelo menu Detalhes da Atração &gt; Gestão Financeira &gt; Relatórios da Atração e oferece nove tipos de relatório (Vendas, Abandono de Carrinho, Ingresso Detalhado, Categorias, Cortesias Emitidas, Validação, Comissões, Venda por Pagamentos e Borderô Resumido).

Requisitos Detalhados

Estrutura Geral e Acesso

O sistema deve exibir o submenu Relatórios da Atração sob Gestão Financeira (em Detalhes da Atração), com os nove tipos de relatório listados. Ao selecionar um tipo, o sistema deve abrir a tela correspondente com título do relatório, área de filtros, tabela/área de dados e botões Imprimir, Download PDF e Download CSV (ou XLSX).

Tipos de Relatório – Resumo

| Tipo                 | Filtros                                                                                                   | Campos fixos                                                                                                                                          | Agrupamento                 | Rodapé      |
|----------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|-------------|
| Vendas               | Período (todos ou início/fim), categoria, agente, agência, tipo ingresso (cortesia, cancelados, vendidos) | Categoria, quantidade, unitário, total                                                                                                                | Categoria                   | Qtd e total |
| Abandono de Carrinho | Período, categoria, agente, agência, tipo ingresso                                                        | Categoria, quantidade, unitário, total (qtd × unitário)                                                                                               | Categoria                   | Qtd e total |
| Ingresso Detalhado   | Período, tipo ingresso (todos/cancelados/vendidos), tipo pagamento                                        | Data, pedido, código ticket, vendedor, categoria, preço, taxa                                                                                         | Pedido, vendedor, pagamento | Qtd e total |
| Categorias           | Período, tipo ingresso, tipo pagamento                                                                    | Data, vendedor, categoria, tipo pagamento, preço, taxa                                                                                                | Categoria                   | Qtd e total |
| Cortesias Emitidas   | Período, agência                                                                                          | Categoria, quantidade, vendedor                                                                                                                       | Categoria                   | Qtd         |
| Validação            | Período, validado/pendentes/validados e pendentes                                                         | Categoria, vendidos, validados, pendentes (vendidos − validados)                                                                                      | Categoria                   | Qtd e total |
| Comissões            | Período, agência, agente                                                                                  | Categoria, quantidade, valor, comissão, total comissão (valor × comissão)                                                                             | Nome agente, atração        | Qtd e total |
| Venda por Pagamentos | Período, tipo pagamento                                                                                   | Tipo pagamento, quantidade, total                                                                                                                     | Tipo pagamento              | Qtd e total |
| Borderô Resumido     | —                                                                                                         | Dados do evento, dados do parceiro, vendas, vendas detalhadas, cortesias, resumo preços, resumo pagamentos, despesas, resumo fechamento, resumo geral | —                           | —           |

| ID        | Requisito                                                                                                                                                                                                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-022.01 | O sistema deve exibir o submenu Relatórios da Atração (sob Gestão Financeira em Detalhes da Atração) com os nove tipos: Vendas, Abandono de Carrinho, Ingresso Detalhado, Categorias, Cortesias Emitidas, Validação, Comissões, Venda por Pagamentos e Borderô Resumido. |
| RF-022.02 | O sistema deve exibir, em cada relatório, título do relatório, área de filtros, área de dados (tabela ou blocos) e botões Imprimir, Download PDF e Download CSV (ou equivalente em planilha).                                                                            |
| RF-022.03 | O sistema deve apresentar filtro de período em todos os relatórios, com opção "Todo o período" ou intervalo data início/fim.                                                                                                                                             |
| RF-022.04 | O sistema deve permitir exportar cada relatório para PDF e para CSV (ou formato de planilha equivalente) em todos os tipos de relatório.                                                                                                                                 |
| RF-022.05 | O sistema deve permitir ao usuário selecionar os campos que serão exibidos no relatório (ex.: botão "Adicionar campo" ou seletor de colunas).                                                                                                                            |
| RF-022.06 | O sistema deve exibir cabeçalho padronizado com logo Curitiba 360, nome do relatório, nome da atração e período selecionado.                                                                                                                                             |
| RF-022.07 | O sistema deve exibir rodapé com data e hora da emissão e, alinhado à direita, página atual/total (ex.: Emitido: segunda-feira 17 novembro 2025 às 15:47:03  Página 1/5).                                                                                                |
| RF-022.08 | O sistema deve calcular automaticamente, a cada agrupamento, o total de registros, soma das quantidades, soma do unitário e soma do total, conforme aplicável ao tipo de relatório.                                                                                      |
| RF-022.09 | O sistema deve exibir o relatório Vendas com filtros (período, categoria, agente, agência, tipo de ingresso), campos fixos (categoria, quantidade, unitário, total), agrupamento por categoria e rodapé Qtd e total.                                                     |
| RF-022.10 | O sistema deve exibir o relatório Abandono de Carrinho com filtros, campos fixos (categoria, quantidade, unitário, total com quantidade × unitário), agrupamento por categoria e rodapé Qtd e total.                                                                     |
| RF-022.11 | O sistema deve exibir o relatório Ingresso Detalhado com filtros (período, tipo ingresso, tipo pagamento), campos fixos (data, pedido, código ticket, vendedor, categoria, preço, taxa), agrupamento por pedido/vendedor/pagamento e rodapé Qtd e total.                 |
| RF-022.12 | O sistema deve exibir o relatório Categorias com filtros (período, tipo ingresso, tipo pagamento), campos fixos (data, vendedor, categoria, tipo pagamento, preço, taxa), agrupamento por categoria e rodapé Qtd e total.                                                |
| RF-022.13 | O sistema deve exibir o relatório Cortesias Emitidas com filtros (período, agência), campos fixos (categoria, quantidade, vendedor), agrupamento por categoria e rodapé Qtd.                                                                                             |
| RF-022.14 | O sistema deve exibir o relatório Validação com filtros (período, validado/pendentes/validados e pendentes), campos fixos (categoria, vendidos, validados, pendentes = vendidos − validados), agrupamento por categoria e rodapé Qtd e total.                            |
| RF-022.15 | O sistema deve exibir o relatório Comissões com filtros (período, agência, agente), campos fixos (categoria, quantidade, valor, comissão, total comissão = valor × comissão em reais), agrupamento por nome agente e atração e rodapé Qtd e total.                       |
| RF-022.16 | O sistema deve exibir o relatório Venda por Pagamentos com filtros (período, tipo pagamento), campos fixos (tipo pagamento, quantidade, total), agrupamento por tipo pagamento e rodapé Qtd e total.                                                                     |
| RF-022.17 | O sistema deve exibir o relatório Borderô Resumido com campos fixos: dados do evento, dados do parceiro comercial, vendas, vendas detalhadas, cortesias, resumo de preços, resumo dos pagamentos, despesas, resumo fechamento e resumo geral.                            |
| RF-022.18 | O sistema deve exibir paginação na área de dados quando houver muitos registros, com seletor de itens por página e indicador "X a Y de Z".                                                                                                                               |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-022.01 | O sistema deve exigir que o usuário preencha pelo menos um filtro e um critério de dados (ex.: categoria ou equivalente) para habilitar a geração do relatório; os botões/imagens para gerar relatório devem permanecer desabilitados até que essa condição seja atendida. |

Critérios de Aceitação

| ID        | Critério                                                                                                                   | Resultado Esperado                                                                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-022.01 | Acessar Detalhes da Atração > Gestão Financeira > Relatórios da Atração como Administrador ou Parceiro Comercial vinculado | Submenu exibe os nove tipos de relatório e permite abrir cada um                                                                                            |
| CA-022.02 | Selecionar Relatório de Vendas e aplicar período + categoria                                                               | Dados exibidos com colunas categoria, quantidade, unitário, total; rodapé com totais; opções Imprimir, PDF e CSV                                            |
| CA-022.03 | Exportar relatório para PDF e para CSV (ou XLSX)                                                                           | Arquivos gerados com cabeçalho (logo, nome relatório, atração, período) e rodapé (data/hora emissão, página atual/total)                                    |
| CA-022.04 | Tentar gerar relatório sem preencher nenhum filtro nem categoria                                                           | Botão/ação de gerar relatório permanece desabilitada ou sistema exibe mensagem orientando o preenchimento                                                   |
| CA-022.05 | Alterar filtro de período em um relatório                                                                                  | Dados e totais atualizados conforme o novo período                                                                                                          |
| CA-022.06 | Abrir Relatório Borderô Resumido                                                                                           | Tela exibe seções: dados evento/parceiro, vendas, vendas detalhadas, cortesias, resumo preços, resumo pagamentos, despesas, resumo fechamento, resumo geral |

Protótipo/Wireframe

Nota: O wireframe dos demais relatórios estarão no arquivo .zip em anexo.

Figura  - WF-032 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Vendas

### 3.23 Detalhes da Atrações/Gestão Financeira/Negociação Financeira/ - Administrador
