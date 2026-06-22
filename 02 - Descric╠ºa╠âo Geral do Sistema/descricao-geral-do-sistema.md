## 2 Descrição Geral do Sistema

### 2.1 Funcionalidades do Produto

O sistema Curitiba 360 está organizado em **módulos funcionais** que atendem diferentes necessidades do negócio. A tabela abaixo apresenta uma visão macro das funcionalidades, que serão detalhadas na Seção 3 (Requisitos Funcionais).

### 2.2 Arquitetura de Módulos

O sistema possui duas grandes áreas:

| Área           | Descrição                        | Usuários                                                           |
|----------------|----------------------------------|--------------------------------------------------------------------|
| Portal Público | Vitrine de atrações e e-commerce | Visitante, Turista                                                 |
| Backoffice     | Área administrativa e de gestão  | Administrador, Parceiro Comercial, Editor, Leitor, Agente, Agência |

### 2.3 Módulos do Backoffice (Administrador)

| ID     | Módulo                  | Descrição                                                                                |
|--------|-------------------------|------------------------------------------------------------------------------------------|
| MOD-01 | Autenticação            | Controle de acesso ao sistema                                                            |
| MOD-02 | Dashboard               | Painel inicial com indicadores gerais, métricas de vendas e visão consolidada do sistema |
| MOD-03 | Perfil                  | Gerenciamento dos dados pessoais e configurações do usuário logado                       |
| MOD-04 | Gestão de Usuários      | Cadastro, edição, ativação/inativação de usuários e atribuição de perfis                 |
| MOD-05 | Gestão de Contratos     | Cadastro e gerenciamento de contratos com parceiros/atrações                             |
| MOD-06 | Configuração Comerciais | Configuração de comissões, repasses e condições de pagamento por parceiro                |
| MOD-07 | Gestão de Atrações      | Módulo principal para gerenciamento completo das atrações (detalhado abaixo)             |
| MOD-08 | Relatórios Financeiros  | Relatórios de vendas, faturamento, repasses e conciliação financeira                     |

### 2.4 Submódulos de Gestão de Atrações

O módulo **Gestão de Atrações (MOD-06)** possui os seguintes submódulos:

| ID        | Submódulo           | Descrição                                                                      |
|-----------|---------------------|--------------------------------------------------------------------------------|
| MOD-06.01 | Categorias          | Gerenciamento das categorias de atrações (museus, parques, restaurantes, etc.) |
| MOD-06.02 | Pesquisar Ingresso  | Busca e consulta de ingressos vendidos com filtros avançados                   |
| MOD-06.03 | Gestão de Ingressos | Gerenciamento dos tipos de ingressos da atração                                |
| MOD-06.04 | Gestão de Cupons    | Criação e gerenciamento de cupons de desconto vinculados à atração             |
| MOD-06.05 | Totais da Atração   | Resumo de vendas, ingressos emitidos e utilizados por atração                  |
| MOD-06.06 | Gráfico Analytics   | Visualização gráfica de métricas e indicadores de performance da atração       |
| MOD-06.07 | Editar Atração      | Edição de dados cadastrais, fotos, descrição e configurações da atração        |
| MOD-06.08 | Agências e Agentes  | Vinculação e gestão de agências/agentes autorizados a vender para a atração    |
| MOD-06.09 | Usuários            | Gestão de usuários vinculados especificamente à atração                        |
| MOD-06.10 | Gestão Financeira   | Controle financeiro específico da atração (comissões, repasses, despesas)      |
| MOD-06.11 | Validar Ingresso    | Interface para validação de ingressos via leitura de QR Code                   |

### 2.5 Usuários e Perfis

O sistema Curitiba 360 possui uma estrutura de perfis que atende tanto usuários finais (turistas) quanto usuários de gestão (backoffice).

### 2.6 Classificação de Usuários

| Classificação      | Área de Acesso        | Perfis                                            |
|--------------------|-----------------------|---------------------------------------------------|
| Usuário Público    | Portal Público        | Visitante, Turista                                |
| Usuário de Negócio | Backoffice            | Administrador, Parceiro Comercial, Editor, Leitor |
| Usuário Vendas     | Backoffice (limitado) | Agência, Agente                                   |

### 2.7 Descrição dos Perfis

Perfis do Portal Público

| ID   | Perfil    | Descrição                                                                                 | Autenticação   |
|------|-----------|-------------------------------------------------------------------------------------------|----------------|
| P01  | Visitante | Usuário que acessa o portal sem cadastro. Pode visualizar atrações, mas não pode comprar. | Não            |
| P02  | Turista   | Usuário cadastrado que pode comprar ingressos, acessar histórico e gerenciar seus dados.  | Sim            |

Perfis do Backoffice - Gestão

| ID   | Perfil             | Descrição                                                                                               |
|------|--------------------|---------------------------------------------------------------------------------------------------------|
| P03  | Administrador      | Acesso total ao sistema. Gerencia usuários, atrações, contratos, financeiro e configurações gerais.     |
| P04  | Parceiro Comercial | Representa uma atração/parceiro. Acesso aos dados e relatórios das atrações vinculadas ao seu cadastro. |
| P05  | Editor             | Pode editar conteúdos de atrações (textos, fotos, horários) mas sem acesso a dados financeiros.         |
| P06  | Leitor             | Acesso somente visualização e validação de ingresso. Não pode criar, editar ou excluir registros.       |

Perfis do Backoffice - Vendas

| ID   | Perfil   | Descrição                                                                                                |
|------|----------|----------------------------------------------------------------------------------------------------------|
| P07  | Agência  | Empresa de turismo autorizada a revender ingressos. Visualiza comissões e relatórios de vendas próprias. |
| P08  | Agente   | Pessoa física vinculada a uma agência ou independente que revende ingressos.                             |

### 2.8 Matriz de Permissões – Backoffice

| Módulo/Funcionalidade        | Admin   | Parceiro Comercial   | Editor   | Leitor   | Agência   | Agente   |
|------------------------------|---------|----------------------|----------|----------|-----------|----------|
| Dashboard                    | ✅       | ⚠️                   | ⚠️       | ❌        | ❌         | ❌        |
| Perfil (próprio)             | ✅       | ✅                    | ✅        | ✅        | ✅         | ✅        |
| Gestão de Usuários           | ✅       | ❌                    | ❌        | ❌        | ❌         | ❌        |
| Gestão de Contratos          | ✅       | ⚠️                   | ❌        | ❌        | ❌         | ❌        |
| **Configuração**  Comerciais | ✅       | ❌                    | ❌        | ❌        | ❌         | ❌        |
| Gestão de Atrações           | ✅       | ⚠️                   | ⚠️       | ❌        | ❌         | ❌        |
| Relatórios Financeiros       | ✅       | ⚠️                   | ❌        | ❌        | ❌         | ❌        |

### 2.9 Matriz de Permissões - Submódulos de Gestão de Atrações

| Submódulo             | Admin   | Parceiro Comercial   | Editor   | Leitor   | Agência   | Agente   |
|-----------------------|---------|----------------------|----------|----------|-----------|----------|
| Categorias            | ✅       | ⚠️                   | ❌        | 👁️       | ❌         | ❌        |
| Pesquisar Ingresso    | ✅       | ⚠️                   | 👁️       | 👁️       | ❌         | ❌        |
| Gestão de Ingressos   | ✅       | ⚠️                   | 👁️       | 👁️       | ❌         | ❌        |
| Gestão de Cupons      | ✅       | ⚠️                   | ⚠️       | 👁️       | ⚠️        | ⚠️       |
| Totais da Atração     | ✅       | ⚠️                   | ❌        | ❌        | ❌         | ❌        |
| Gráfico Analytics     | ✅       | ⚠️                   | ❌        | ❌        | ❌         | ❌        |
| Editar Atração        | ✅       | ⚠️                   | ⚠️       | ❌        | ❌         | ❌        |
| Agências e Agentes    | ✅       | ⚠️                   | ❌        | 👁️       | 👁️        | 👁️       |
| Usuários (da atração) | ✅       | ⚠️                   | ❌        | 👁️       | ❌         | ❌        |
| Gestão Financeira     | ✅       | ⚠️                   | ❌        | ❌        | ❌         | ❌        |
| Validar Ingresso      | ✅       | ⚠️                   | ❌        | ⚠️       | ❌         | ❌        |

Legenda:

| Símbolo   | Significado                                                         |
|-----------|---------------------------------------------------------------------|
| ✅         | Acesso total (criar, editar, excluir, visualizar)                   |
| ⚠️        | Acesso restrito (apenas registros vinculados ao seu perfil/atração) |
| 👁️        | Somente visualização                                                |
| ❌         | Sem acesso                                                          |

### 2.10 Regras de Vinculação de Perfis

| RV-ID   | Regra                                                                               |
|---------|-------------------------------------------------------------------------------------|
| RV-01   | Um Parceiro Comercial deve estar vinculado a pelo menos uma atração                 |
| RV-02   | Um Editor deve estar vinculado a pelo menos uma atração para poder editá-la         |
| RV-03   | Um Agente pode estar vinculado a uma Agência ou ser independente                    |
| RV-04   | Uma Agência pode ter múltiplos Agentes vinculados                                   |
| RV-05   | Um Agente/Agência deve ser autorizado pela atração para poder vender seus ingressos |
| RV-06   | O Administrador tem acesso a todas as atrações, independente de vinculação          |

### 2.11 Restrições

O sistema deve ser web responsivo e trilíngue (Português, espanhol e Inglês).

O tempo de navegação e compra deve ser rápido e intuitivo, minimizando etapas obrigatórias.

O sistema deve ser compatível com as exigências da LGPD (consentimento para uso de dados e campanhas).

A primeira versão não incluirá aplicativos nativos (Android/iOS).

Operações de pagamento dependerão de gateways externos.

Disponibilidade e regras de cada atração dependerão dos parceiros (responsáveis por manter informações atualizadas).

### 2.12 Suposições e Dependências

Parceiros fornecerão dados consistentes e atualizados sobre suas atrações e ofertas.

O correto funcionamento da plataforma depende da disponibilidade dos serviços de terceiros (ex.: gateways de pagamento, provedores de envio de mensagens).

O QR Code será a forma padrão de ingresso.
