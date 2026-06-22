**DOCUMENTO DE REQUISITOS DE SOFTWARE**

05/02/2026

## Sumário

[1.	Introdução	4](.)

[1.1.	Objetivo	4](.)

[1.2.	Objetivo do Sistema	5](.)

[1.3.	Escopo	5](.)

[1.3.1.	Escopo Positivo (Incluso nesta versão)	5](.)

[1.3.2.	Escopo Negativo (Exclusões)	6](.)

[1.4.	Histórico de Revisões	6](.)

[1.5.	Garantia	6](.)

[1.6.	Definições, Acrônimos e Abreviações	6](.)

[1.7.	Referências	7](.)

[2.	Descrição Geral do Sistema	7](.)

[2.1.	Funcionalidades do Produto	7](.)

[2.1.1.	Arquitetura de Módulos	7](.)

[2.1.2.	Módulos do Backoffice (Administrador)	8](.)

[2.1.3.	Submódulos de Gestão de Atrações	8](.)

[2.2.	Usuários e Perfis	9](.)

[2.2.1.	Classificação de Usuários	9](.)

[2.2.2.	Descrição dos Perfis	9](.)

[2.2.3.	Matriz de Permissões – Backoffice	9](.)

[2.2.4.	Matriz de Permissões - Submódulos de Gestão de Atrações	10](.)

[2.2.5.	Regras de Vinculação de Perfis	10](.)

[2.3.	Restrições	11](.)

[2.4.	Suposições e Dependências	11](.)

[3.	Requisitos Funcionais	11](.)

[3.1.	Autenticação com E-mail e Senha	11](.)

[3.2.	Tela Inicial	13](.)

[3.3.	Dashboard – Administrador	15](.)

[3.4.	Detalhes da Atração / Totais da Atração - Administrador	17](.)

[3.5.	Tela de Perfil	22](.)

[3.6.	Gestão de Usuários - Administrador	26](.)

[3.7.	Cadastro de Usuários - Administrador	32](.)

[3.8.	Tela Gestão de Contratos - Administrador	38](.)

[3.9.	Incluir Contratos - Administrador	44](.)

[3.10.	Configuração Comerciais - Administrador	51](.)

[3.11.	Informações Financeiras (Administrador)	57](.)

[3.12.	Tela de Gestão de Atrações - Administrador	61](.)

[3.13.	Tela de Gestão de Atrações/Adicionar Atração - Administrador	65](.)

[3.14.	Detalhes da Atrações/Categorias – Administrador	73](.)

[3.15.	Detalhes da Atrações/Pesquisar Ingresso – Administrador	77](.)

[3.16.	Detalhes da Atrações/Pesquisar Ingresso/Detalhes – Administrador	81](.)

[3.17.	Detalhes da Atrações/Gestão de Ingressos – Administrador.	84](.)

[3.18.	Detalhes da Atrações/Gestão de Cupons – Administrador	89](.)

[3.19.	Detalhes da Atrações/Gráficos Analytics - Administrador	95](.)

[3.20.	Detalhes da Atrações/Editar da Atração - Administrador	100](.)

[3.21.	Detalhes da Atrações/Usuários - Administrador	102](.)

[3.22.	Detalhes da Atrações/Gestão Financeira/Relatórios da Atração- Administrador	107](.)

[3.23.	Detalhes da Atrações/Gestão Financeira/Negociação Financeira/ - Administrador	112](.)

[3.24.	Detalhes da Atrações/Gestão Financeira/Resumo das Despesas - Administrador	116](.)

[3.25.	Detalhes da Atrações/Tela de Validação de Ingressos	122](.)

[4.	Requisitos Não Funcionais	128](.)

[4.1.	Desempenho	128](.)

[4.2.	Usabilidade	128](.)

[4.3.	Segurança	129](.)

[4.4.	Portabilidade e Compatibilidade	129](.)

[4.5.	Confiabilidade e Disponibilidade	129](.)

[4.6.	Manutenibilidade e Evolução	129](.)

[4.7.	Armazenamento e Dados	129](.)

[5.	Casos de Uso	129](.)

[5.1.	CU-001 - Realizar Login	129](.)

[5.2.	CU-002 - Realizar Logout	130](.)

[5.3.	CU-003 - Recuperar Senha	130](.)

[5.4.	CU-004 - Visualizar Dashboard	131](.)

[5.5.	CU-005 - Gerenciar Perfil	131](.)

[5.6.	CU-006 - Cadastrar Usuário	132](.)

[5.7.	CU-007 - Editar Usuário	132](.)

[5.8.	CU-008 - Gerenciar Contratos	133](.)

[5.9.	CU-009 - Cadastrar Condições Comerciais	133](.)

[5.10.	CU-010 - Cadastrar Informações Financeiras	134](.)

[5.11.	CU-011 - Cadastrar Atração	134](.)

[5.12.	CU-012 - Editar Atração	135](.)

[5.13.	CU-013 - Visualizar Atrações no Mapa	135](.)

[5.14.	CU-014 - Criar Pacote de Ingressos	135](.)

[5.15.	CU-015 - Visualizar Totais da Atração	136](.)

[5.16.	CU-016 - Gerenciar Categorias da Atração	136](.)

[5.17.	CU-017 - Pesquisar Ingresso	137](.)

[5.18.	CU-018 - Gerenciar Ingressos da Atração	137](.)

[5.19.	CU-019 - Gerenciar Cupons da Atração	138](.)

[5.20.	CU-020 - Gerar QR Code de Cupom	138](.)

[5.21.	CU-021 - Visualizar Gráficos e Analytics	139](.)

[5.22.	CU-022 - Gerenciar Usuários da Atração	139](.)

[5.23.	CU-023 - Visualizar Negociação Financeira	140](.)

[5.24.	CU-024 - Visualizar Resumo das Despesas	140](.)

[5.25.	CU-025 - Solicitar Repasse	141](.)

[5.26.	CU-026 - Autorizar/Registrar Repasse	141](.)

[5.27.	CU-027 - Validar Ingresso (Leitura QR Code)	142](.)

[5.28.	CU-028 - Realizar Checklist de Visita	142](.)

[5.29.	CU-029 - Gerenciar Imagens da Atração	143](.)

[6.	Anexos	143](.)

[7.	Entregas do Projeto	145](.)

## 1 Introdução

### 1.1 Objetivo

Este documento tem como objetivo especificar os requisitos funcionais e não funcionais do sistema Curitiba 360, servindo como base para o desenvolvimento, testes e validação da aplicação.

Público-alvo deste documento:

Equipe de desenvolvimento

Analistas de qualidade (QA)

Gerentes de projeto

Stakeholders e representantes do cliente

### 1.2 Objetivo do Sistema

O sistema Curitiba 360 tem como propósito principal ser uma plataforma digital centralizada para:

Divulgação de atrações turísticas de Curitiba e região metropolitana

Comercialização de ingressos individuais e pacotes turísticos

Gestão administrativa de parceiros, atrações, vendas e validação de ingressos

Principais benefícios esperados:

Facilitar a aquisição de ingressos para turistas de forma simples e rápida

Integrar múltiplas atrações (eventos, restaurantes, passeios) em pacotes personalizáveis

Fornecer recursos de gestão de vendas e relatórios para administradores

Permitir validação de ingressos via QR Code

### 1.3 Escopo

### 1.4 Escopo Positivo (Incluso nesta versão)

O sistema contemplará os seguintes módulos e funcionalidades:

Módulo Web (Responsivo)

| ID    | Funcionalidade      | Descrição                                             |
|-------|---------------------|-------------------------------------------------------|
| MW-01 | Plataforma Web      | Aplicação web responsiva para desktop e mobile        |
| MW-02 | Multilíngue         | Suporte a 3 idiomas: português, inglês e espanhol     |
| MW-03 | Vitrine de Atrações | Catálogo de atrações turísticas com busca e filtros   |
| MW-04 | E-commerce          | Carrinho de compras e checkout para ingressos/pacotes |

Módulo Administrativo

| ID    | Funcionalidade      | Descrição                                               |
|-------|---------------------|---------------------------------------------------------|
| MA-01 | Gestão de Usuários  | CRUD de usuários com controle de perfis e permissões    |
| MA-02 | Gestão de Atrações  | Cadastro e gerenciamento de atrações turísticas         |
| MA-03 | Gestão de Contratos | Controle de contratos com parceiros/atrações            |
| MA-04 | Gestão de Ingressos | Criação de tipos de ingressos, preços e disponibilidade |
| MA-05 | Gestão de Cupons    | Criação e controle de cupons de desconto                |
| MA-06 | Relatórios          | Dashboards e relatórios de vendas e financeiro          |
| MA-07 | Validação QR Code   | Sistema de validação de ingressos via QR Code           |

Integrações

| ID     | Funcionalidade       | Descrição                                    |
|--------|----------------------|----------------------------------------------|
| INT-01 | Gateway de Pagamento | Integração com meio de pagamento (a definir) |
| INT-02 | Envio de E-mails     | Notificações e envio de ingressos por e-mail |

### 1.5 Escopo Negativo (Exclusões)

Os itens abaixo NÃO fazem parte do escopo desta versão:

| ID    | Item Excluído                                                | Justificativa                              |
|-------|--------------------------------------------------------------|--------------------------------------------|
| EX-01 | Aplicativo Mobile Nativo (iOS/Android)                       | Previsto para versão 2.0                   |
| EX-02 | Integração com redes sociais                                 | Não solicitado pelo cliente                |
| EX-03 | Sistema de avaliações/reviews                                | Não contemplado nos requisitos             |
| EX-04 | Chat de atendimento ao cliente                               | Fora do escopo inicial                     |
| EX-05 | Integração em tempo real com todos os sistemas dos parceiros | Haverá cadastros manuais quando necessário |
| EX-06 | Emissão de notas fiscais                                     | Fora do escopo inicial                     |

Nota: O sistema será desenvolvido com design responsivo, garantindo boa experiência em dispositivos móveis mesmo sem aplicativo nativo.

### 1.6 Histórico de Revisões

|   Versão | Data       | Autor        | Descrição da Alteração      |
|----------|------------|--------------|-----------------------------|
|        1 | 05/02/2026 | System Wiser | Versão inicial do documento |
|        2 |            |              |                             |
|        3 |            |              |                             |

### 1.7 Garantia

A garantia do software será válida por um período de **30 dias corridos** após a entrada em produção. Durante este período, correções de defeitos ou falhas que comprometam o funcionamento especificados neste documento serão realizadas sem custo adicional.

A garantia **não cobre** :

Solicitações de novas funcionalidades ou alterações nos requisitos após a entrega.

Mau uso do sistema ou falhas resultantes de operações fora do escopo previsto.

Para novas inclusões ou alterações após o período de garantia, ou aquelas não especificadas no documento, um novo contrato de suporte ou solicitação de mudança deverá ser formalizado.

Toda solicitação de correção deverá ser validada e autorizada pelo responsável do cliente, respeitando os prazos definidos entre as partes no acordo de serviço.

### 1.8 Definições, Acrônimos e Abreviações

**IEEE:** Institute of Electrical and Electronic Engineers (Instituto de Engenheiros Eletricistas e Eletrônicos).

**Atração:** Qualquer ponto turístico, evento, restaurante ou passeio cadastrado no sistema

**Pacote:** Conjunto de ingressos para múltiplas atrações vendido com desconto.

**Ingresso:** Ticket digital que dá direito de acesso a uma atração.

**Parceiro:** Empresa ou estabelecimento que oferece atrações na plataforma.

**Cupom:** Código promocional que oferece desconto na compra.

**Voucher:** Comprovante digital do ingresso adquirido.

**RF** : Requisito Funcional.

**RNF** : Requisito Não Funcional.

**RN:** Regra de Negócio.

**UC:** Caso de Uso (Use Case).

**QR Code:** Quick Response Code - Código de resposta rápida .

**CRUD:** Create, Read, Update, Delete.

**API:** Application Programming Interface.

**MVP:** Minimum Viable Product.

**SRS:** Software Requirements Specification.

### 1.9 Referências

IEEE Std 830-1998 – IEEE Recommended Practice for Software Requirements Specifications.

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

## 3 Requisitos Funcionais

### 3.1 Autenticação com E-mail e Senha

**ID:** RF-001

Módulo: Autenticação

Perfis com Acesso: Todos (Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente)

**Prioridade:** Alta (Essencial)

Descrição: O sistema deve permitir que usuários cadastrados realizem autenticação utilizando e-mail e senha para acessar as funcionalidades do Backoffice.

**Requisitos Detalhados**

| ID        | Requisito                                                                                                      |
|-----------|----------------------------------------------------------------------------------------------------------------|
| RF-001.01 | O sistema deve exibir uma tela de login com os campos: E-mail e Senha                                          |
| RF-001.02 | O sistema deve validar as credenciais informadas contra a base de dados                                        |
| RF-001.03 | O sistema deve exibir mensagem de erro genérica em caso de credenciais inválidas                               |
| RF-001.04 | O sistema deve redirecionar o usuário para a tela inicial correspondente ao seu perfil após login bem-sucedido |
| RF-001.05 | O sistema deve disponibilizar a opção "Esqueci minha senha"                                                    |
| RF-001.06 | O sistema deve bloquear a conta após 5 tentativas inválidas consecutivas                                       |
| RF-001.07 | O sistema deve manter a sessão ativa por 8 horas de inatividade                                                |
| RF-001.08 | O sistema deve permitir que o usuário realize logout a qualquer momento                                        |
| RF-001.09 | O sistema deve permitir que o usuário realize a criação da conta ou login com Google ou Facebook               |

**Regras de Negócio**

| ID        | Regra                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------|
| RN-001.01 | A mensagem de erro deve ser genérica: "E-mail ou senha inválidos" (não informar qual campo está errado por segurança) |
| RN-001.02 | A senha deve ter no mínimo 8 caracteres, contendo letras maiúsculas, minúsculas e números                             |
| RN-001.03 | O e-mail deve ser único no sistema (não permitir duplicidade)                                                         |
| RN-001.04 | Usuários inativos não podem realizar login                                                                            |
| RN-001.05 | Após bloqueio por tentativas inválidas, o desbloqueio deve ser feito pelo Administrador                               |
| RN-001.06 | Ao solicitar recuperação de senha, o sistema deve enviar uma senha provisória por e-mail                              |
| RN-001.07 | Ao fazer login com senha provisória, o sistema deve obrigar a troca de senha                                          |

Critérios de Aceitação

| ID        | Critério                             | Resultado Esperado                                                                 |
|-----------|--------------------------------------|------------------------------------------------------------------------------------|
| CA-001.01 | Login com credenciais válidas        | Usuário é redirecionado para a tela inicial do seu perfil                          |
| CA-001.02 | Login com e-mail inválido            | Mensagem "E-mail ou senha inválidos"                                               |
| CA-001.03 | Login com senha inválida             | Mensagem "E-mail ou senha inválidos"                                               |
| CA-001.04 | Login com usuário inativo            | Mensagem "Usuário inativo. Entre em contato com o administrador"                   |
| CA-001.05 | 5 tentativas inválidas consecutivas  | Conta bloqueada + mensagem "Conta bloqueada. Entre em contato com o administrador" |
| CA-001.06 | Solicitar recuperação de senha       | E-mail enviado com senha provisória em até 5 minutos                               |
| CA-001.07 | Login com senha provisória           | Sistema exibe tela obrigatória de troca de senha                                   |
| CA-001.08 | Sessão expira após 8h de inatividade | Usuário é redirecionado para tela de login                                         |

**Protótipo/Wireframe**

Figura  WF-001 - Tela de login.png

### 3.2 Tela Inicial

**ID:** RF-002

**Módulo:** Home

**Perfis com Acesso:** Todos os perfis autenticados

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve exibir uma tela inicial personalizada de acordo com o perfil do usuário logado, apresentando o menu de navegação lateral com as opções disponíveis para cada perfil e informações contextuais.

Requisitos Detalhados

| ID        | Requisito                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------|
| RF-002.01 | O sistema deve exibir um menu lateral com as opções de navegação conforme o perfil do usuário |
| RF-002.02 | O sistema deve exibir o nome do usuário logado no cabeçalho                                   |
| RF-002.03 | O sistema deve exibir a foto do usuário (se cadastrada) ou um avatar padrão                   |
| RF-002.04 | O sistema deve disponibilizar um botão de "Sair" (logout) no cabeçalho                        |
| RF-002.05 | O sistema deve exibir um pop-up de confirmação ao clicar em "Sair"                            |
| RF-002.06 | O sistema deve permitir recolher/expandir o menu lateral                                      |

Regras de Negócio

| ID        | Regra                                                                                                                                                                         |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-002.01 | O menu deve exibir apenas as opções disponíveis para o perfil do usuário logado                                                                                               |
| RN-002.02 | O perfil  **Administrador**  deve visualizar: Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| RN-002.03 | Os perfis  **Parceiro Comercial, Editor, Leitor, Agência, Agente**  terão suas telas definidas na versão 2.0 do sistema                                                       |
| RN-002.04 | O sistema deve destacar visualmente o menu ativo/selecionado                                                                                                                  |

Menus por Perfil (Versão 1.0)

| Perfil             | Menus Disponíveis                                                                                                               |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Administrador      | Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| Parceiro Comercial | Definido na v2.0                                                                                                                |
| Editor             | Definido na v2.0                                                                                                                |
| Leitor             | Definido na v2.0                                                                                                                |
| Agência            | Definido na v2.0                                                                                                                |
| Agente             | Definido na v2.0                                                                                                                |

Critérios de Aceitação

| ID        | Critério                         | Resultado Esperado                                                                                                                          |
|-----------|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| CA-002.01 | Login como Administrador         | Menu exibe: Dashboard, Perfil, Gestão de Usuários, Gestão de Contratos, Configuração Comerciais, Gestão de Atrações, Relatórios Financeiros |
| CA-002.02 | Clicar em "Sair"                 | Pop-up de confirmação "Deseja realmente sair?" com opções "Sim" e "Não"                                                                     |
| CA-002.03 | Confirmar logout                 | Usuário redirecionado para tela de login e sessão encerrada                                                                                 |
| CA-002.04 | Cancelar logout                  | Pop-up fechado e usuário permanece logado                                                                                                   |
| CA-002.05 | Verificar nome e foto do usuário | Nome e foto (ou avatar) exibidos corretamente no cabeçalho                                                                                  |

Protótipo/Wireframe

Figura  - WF-002 - Dashboard

### 3.3 Dashboard – Administrador

**ID:** RF-003

**Módulo:** Dashboard

**Perfis com Acesso** : Administrador

**Prioridade:** Alta (Essencial)

Descrição: O sistema deve exibir um painel de controle (Dashboard) para o Administrador com indicadores consolidados de vendas, atrações e métricas gerais do sistema, permitindo uma visão geral do negócio.

Requisitos Detalhados

| ID        | Requisito                                                                          |
|-----------|------------------------------------------------------------------------------------|
| RF-003.01 | O sistema deve exibir as atrações em cards com indicadores resumidos (KPIs)        |
| RF-003.02 | O sistema deve exibir uma lista das atrações cadastradas com informações resumidas |
| RF-003.03 | O sistema deve permitir filtrar os dados por período (data inicial e data final)   |
| RF-003.04 | O sistema deve permitir clicar em uma atração para visualizar seus detalhes        |
| RF-003.05 | O sistema deve exibir gráficos de vendas e/ou indicadores visuais                  |
| RF-003.06 | O sistema deve permitir pesquisar atrações pelo nome, cidade, estado, data e id.   |
| RF-003.07 | O sistema deverá exibir botão para ordenação por nome ou data.                     |

Regras de Negócio

| ID        | Regra                                                                       |
|-----------|-----------------------------------------------------------------------------|
| RN-003.01 | O Dashboard é exclusivo para o perfil  **Administrador**  nesta versão      |
| RN-003.02 | Os dados exibidos devem ser atualizados em tempo real ou com refresh manual |
| RN-003.03 | O filtro de período padrão deve considerar os últimos 30 dias               |

Indicadores Sugeridos (Cards)

| Indicador          | Descrição                                    |
|--------------------|----------------------------------------------|
| Ingressos Vendidos | Quantidade de ingressos vendidos no período  |
| Cortesias          | Quantidade de ingressos cortesia emitidos    |
| Total de ingressos | Quantidade de total de ingressos emitidos    |
| Total de Vendas    | Valor total de vendas no período selecionado |

Critérios de Aceitação

| ID        | Critério                             | Resultado Esperado                                            |
|-----------|--------------------------------------|---------------------------------------------------------------|
| CA-003.01 | Acessar Dashboard como Administrador | Cards de KPIs exibidos com dados corretos                     |
| CA-003.02 | Aplicar filtro de período            | Dados atualizados conforme período selecionado                |
| CA-003.03 | Clicar em uma atração da lista       | Sistema redireciona para tela de Detalhes da Atração (RF-004) |
| CA-003.04 | Pesquisar atração por nome           | Lista filtrada exibindo apenas atrações correspondentes       |
| CA-003.05 | Acessar Dashboard com outro perfil   | Acesso negado ou menu não visível                             |

Protótipo/Wireframe

Figura  - WF-002 - Dashboard

### 3.4 Detalhes da Atração / Totais da Atração - Administrador

**ID:** RF-004

Módulo: Gestão de Atrações &gt; Totais da Atração

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve exibir uma tela de detalhes ao selecionar uma atração (via Dashboard ou menu Gestão de Atrações), apresentando:

- Informações da atração selecionada (nome, foto, localização)
- Menu lateral com submódulos de gestão da atração
- Cards com indicadores consolidados de vendas, ingressos e formas de pagamento
- Filtros de período para análise dos dados

Esta tela é o ponto central de gestão de cada atração, dando acesso a todos os submódulos relacionados.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-004.01 | O sistema deve exibir o nome da atração selecionada no cabeçalho da área de conteúdo       |
| RF-004.02 | O sistema deve exibir a foto/imagem da atração no painel lateral esquerdo                  |
| RF-004.03 | O sistema deve exibir a localização da atração (bairro - cidade) abaixo da foto            |
| RF-004.04 | O sistema deve exibir um menu lateral com os submódulos disponíveis para gestão da atração |
| RF-004.05 | O sistema deve destacar visualmente o submódulo ativo/selecionado no menu                  |
| RF-004.06 | O sistema deve manter o contexto da atração selecionada ao navegar entre submódulos        |
| RF-004.07 | O sistema deve disponibilizar link para retornar ao Dashboard no menu lateral              |

Filtros de Período

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-004.08 | O sistema deve exibir botões de filtro rápido: "Tudo", "Hoje", "7 Dias", "30 Dias"     |
| RF-004.09 | O sistema deve exibir opção "Período" para seleção de intervalo de datas personalizado |
| RF-004.10 | O sistema deve atualizar todos os cards ao alterar o filtro de período                 |
| RF-004.11 | O sistema deve manter o filtro selecionado ao navegar entre submódulos                 |
| RF-004.12 | O filtro padrão ao acessar a tela deve ser "30 Dias"                                   |

Cards de Indicadores (KPIs)

| ID        | Requisito                                                                                                                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------|
| RF-004.13 | O sistema deve exibir cards organizados em grid responsivo                                                                   |
| RF-004.14 | Cada card deve exibir: título, descrição, quantidade de ingressos, percentual de variação, e métricas específicas            |
| RF-004.15 | O percentual de variação deve comparar com o período anterior equivalente                                                    |
| RF-004.16 | O sistema deve exibir indicadores visuais de variação positiva (verde/seta para cima) ou negativa (vermelho/seta para baixo) |

Cards de Indicadores Obrigatórios

Card 1: Ingressos Vendidos

| Campo                   | Descrição                                             |
|-------------------------|-------------------------------------------------------|
| Título                  | Ingressos Vendidos                                    |
| Subtítulo               | Ingressos Vendidos no período                         |
| Quantidade de Ingressos | Total de ingressos vendidos (unidades)                |
| Variação %              | Comparativo com período anterior                      |
| Valor das Vendas        | Valor total em R$                                     |
| Ticket Médio            | Valor médio por ingresso (R$)                         |
| Indicador de Meta       | "Acima da meta" / "Abaixo da meta" (quando aplicável) |

Card 2: Ingressos Emitidos

| Campo                   | Descrição                        |
|-------------------------|----------------------------------|
| Título                  | Ingressos Emitidos               |
| Subtítulo               | Ingressos Emitidos no período    |
| Quantidade de Ingressos | Total de ingressos emitidos      |
| Variação %              | Comparativo com período anterior |
| Cortesias               | Quantidade de ingressos cortesia |
| Total                   | Soma de vendidos + cortesias     |

Card 3: Ingressos Reservados

| Campo                   | Descrição                        |
|-------------------------|----------------------------------|
| Título                  | Ingressos Reservados             |
| Subtítulo               | Ingressos Reservados no período  |
| Quantidade de Ingressos | Total de ingressos em reserva    |
| Variação %              | Comparativo com período anterior |
| Quantidade              | Valor total reservado (R$)       |
| Total                   | Valor unitário médio (R$)        |

Card 4: Ingressos Validação

| Campo                   | Descrição                                      |
|-------------------------|------------------------------------------------|
| Título                  | Ingressos Validação                            |
| Subtítulo               | Ingressos Validados no período                 |
| Quantidade de Ingressos | Total de ingressos processados para validação  |
| Variação %              | Comparativo com período anterior               |
| Validados               | Quantidade efetivamente validados (utilizados) |
| Pendentes               | Quantidade ainda não validados                 |

Cards de Vendas por Forma de Pagamento

O sistema deve exibir um card para cada forma de pagamento disponível:

| Card    | Título                           | Subtítulo                           |
|---------|----------------------------------|-------------------------------------|
| Card 5  | Vendas no Dinheiro               | Vendas em dinheiro no período       |
| Card 6  | Vendas no C. Débito              | Vendas no cartão débito no período  |
| Card 7  | Vendas no C. Crédito             | Vendas no cartão crédito no período |
| Card 8  | Vendas no C. Crédito Parcelado   | Vendas no cartão crédito no período |
| Card 9  | Vendas no PIX                    | Vendas no PIX no período            |
| Card 10 | Vendas por depósito, TED, etc... | Vendas por depósito no período      |

Estrutura de cada card de pagamento:

| Campo                   | Descrição                                            |
|-------------------------|------------------------------------------------------|
| Quantidade de Ingressos | Total de ingressos vendidos nesta forma de pagamento |
| Variação %              | Comparativo com período anterior                     |
| Unidades Vendidas       | Label descritivo                                     |
| Quantidade              | Número de transações                                 |
| Total                   | Valor total em R$                                    |

Menu Lateral - Submódulos

|   Ordem | Submódulo          | Observação                          |
|---------|--------------------|-------------------------------------|
|       1 | Dashboard          | Retorna ao Dashboard geral          |
|       2 | Totais da Atração  | Tela atual (selecionada por padrão) |
|       3 | Categorias         | Gestão de categorias de ingressos   |
|       4 | Pesquisar Ingresso | Busca de ingressos vendidos         |
|       5 | Gestão de Cupons   | Criação e gestão de cupons          |
|       6 | Gráficos Analytics | Visualização gráfica de métricas    |
|       7 | Editar da Atração  | Edição de dados cadastrais          |
|       8 | Agências e Agentes | Vinculação de canais de vendas      |
|       9 | Usuários           | Gestão de usuários da atração       |
|      10 | Gestão Financeira  | Submenu com opções financeiras      |
|      11 | Validar Ingressos  | Interface de validação QR Code      |

Nota: O submódulo "Gestão Financeira" é um menu expansível que contém os seguintes submenus: Relatórios da Atração (Vendas, Abandono de Carrinho, Ingresso Detalhado, Categorias, Cortesias Emitidas, Validação, Comissões, Venda por Pagamentos, Borderô Resumido), Negociação Financeira (Informações Financeiras, Condições Comerciais) e Resumo das Despesas.

Regras de Negócio

| ID        | Regra                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------|
| RN-004.01 | Ao acessar os detalhes de uma atração, o submódulo "Totais da Atração" deve ser exibido por padrão |
| RN-004.02 | O filtro de período considera a  **data de venda**  do ingresso                                    |
| RN-004.03 | O percentual de variação compara o período selecionado com o período anterior de igual duração     |
| RN-004.04 | Se não houver dados no período anterior para comparação, exibir "N/A" no percentual                |
| RN-004.05 | Cards com valor zero devem ser exibidos normalmente (não ocultar)                                  |
| RN-004.06 | O Ticket Médio é calculado como: Valor das Vendas ÷ Quantidade de Ingressos Vendidos               |
| RN-004.07 | Ingressos cortesia não devem ser contabilizados no valor de vendas                                 |
| RN-004.08 | O indicador "Acima/Abaixo da meta" só é exibido se houver meta configurada para a atração          |
| RN-004.09 | Ao clicar em "Dashboard" no menu, o sistema retorna ao Dashboard geral (RF-003)                    |
| RN-004.10 | O submódulo "Gestão Financeira" deve expandir para exibir suas subopções                           |

Cálculos dos Indicadores

| Indicador         | Fórmula                                                                         |
|-------------------|---------------------------------------------------------------------------------|
| Ticket Médio      | Valor Total das Vendas ÷ Quantidade de Ingressos Vendidos                       |
| Variação %        | ((Valor Período Atual - Valor Período Anterior) ÷ Valor Período Anterior) × 100 |
| Total Emitidos    | Ingressos Vendidos + Cortesias                                                  |
| Taxa de Validação | (Ingressos Validados ÷ Ingressos Emitidos) × 100                                |

Critérios de Aceitação

| ID        | Critério                                      | Resultado Esperado                                              |
|-----------|-----------------------------------------------|-----------------------------------------------------------------|
| CA-004.01 | Acessar detalhes de uma atração via Dashboard | Tela exibe nome, foto, localização e cards com dados da atração |
| CA-004.02 | Visualizar submódulo "Totais da Atração"      | Submódulo destacado no menu e cards de indicadores exibidos     |
| CA-004.03 | Clicar no filtro "Hoje"                       | Todos os cards atualizam com dados do dia atual                 |
| CA-004.04 | Clicar no filtro "7 Dias"                     | Todos os cards atualizam com dados dos últimos 7 dias           |
| CA-004.05 | Clicar no filtro "30 Dias"                    | Todos os cards atualizam com dados dos últimos 30 dias          |
| CA-004.06 | Clicar no filtro "Período"                    | Exibe seletor de data inicial e data final                      |
| CA-004.07 | Selecionar período personalizado              | Cards atualizam com dados do intervalo selecionado              |
| CA-004.08 | Verificar card "Ingressos Vendidos"           | Exibe quantidade, valor, ticket médio e variação %              |
| CA-004.09 | Verificar card "Ingressos Emitidos"           | Exibe quantidade, cortesias e total                             |
| CA-004.10 | Verificar card "Ingressos Validação"          | Exibe quantidade, validados e pendentes                         |
| CA-004.11 | Verificar cards de formas de pagamento        | Cada forma exibe quantidade, número de transações e valor total |
| CA-004.12 | Variação positiva                             | Exibe percentual em verde com seta para cima                    |
| CA-004.13 | Variação negativa                             | Exibe percentual em vermelho com seta para baixo                |
| CA-004.14 | Clicar em "Categorias" no menu                | Sistema navega para submódulo mantendo contexto da atração      |
| CA-004.15 | Clicar em "Dashboard" no menu                 | Sistema retorna ao Dashboard geral                              |
| CA-004.16 | Clicar em "Sign Out"                          | Sistema realiza logout e redireciona para login                 |
| CA-004.17 | Atração sem vendas no período                 | Cards exibem valor "0" (não ocultar cards)                      |
| CA-004.18 | Atração sem período anterior para comparação  | Variação exibe "N/A"                                            |

Protótipo/Wireframe

Figura  - WF-003 - Detalhes da Atração/Totais da atração

### 3.5 Tela de Perfil

**ID:** RF-005

Módulo: Perfil

Perfis com Acesso: Todos os perfis autenticados

**Prioridade:** Média

**Descrição** : O sistema deve disponibilizar um modal de perfil onde o usuário autenticado pode visualizar e editar suas configurações pessoais. Algumas funcionalidades são exclusivas para perfis específicos (Parceiro Comercial).

Requisitos Detalhados

| ID        | Requisito                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------|
| RF-005.01 | O sistema deve exibir o modal de perfil ao clicar no menu "Perfil" ou no nome/foto do usuário |
| RF-005.02 | O modal deve exibir o título "Perfil" com subtítulo "Gerencie suas configurações de perfil"   |
| RF-005.03 | O modal deve exibir os botões "Sair" (fechar sem salvar) e "Salvar" no cabeçalho              |
| RF-005.04 | O sistema deve validar os campos obrigatórios antes de salvar                                 |
| RF-005.05 | O sistema deve exibir mensagem de sucesso após salvar alterações                              |

Campos do Formulário

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-005.06 | O sistema deve exibir área para  **Foto de Perfil**  com opções "Carregar nova foto" e "Apagar" |
| RF-005.07 | O sistema deve exibir campos  **Primeiro nome**  e  **Último nome**  (editáveis)                |
| RF-005.08 | O sistema deve exibir campo  **CPF/CNPJ**  (somente visualização)                               |
| RF-005.09 | O sistema deve exibir campo  **E-mail de contato**  principal (somente visualização)            |
| RF-005.10 | O sistema deve exibir campo  **Telefone**  (editável)                                           |
| RF-005.11 | O sistema deve exibir campo  **Idioma padrão**  (editável via select)                           |

Funcionalidades Exclusivas - Parceiro Comercial

| ID        | Requisito                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| RF-005.12 | Para perfil  **Parceiro Comercial**  : exibir botão "Adicionar outro email"                          |
| RF-005.13 | Para perfil  **Parceiro Comercial**  : exibir seção "Integração da conta" com opção Google Analytics |
| RF-005.14 | O sistema deve permitir conectar/desconectar conta do Google Analytics                               |

Campos do Formulário - Detalhamento

| Campo             | Tipo     | Editável   | Obrigatório   | Observação                                  |
|-------------------|----------|------------|---------------|---------------------------------------------|
| Foto de Perfil    | Upload   | ✅          | ❌             | PNG, JPEG - máx 5MB                         |
| Primeiro nome     | Texto    | ✅          | ✅             | Máximo 50 caracteres                        |
| Último nome       | Texto    | ✅          | ✅             | Máximo 50 caracteres                        |
| CPF/CNPJ          | Texto    | ❌          | -             | Apenas visualização                         |
| E-mail principal  | E-mail   | ❌          | -             | Apenas visualização (usado no login)        |
| E-mail secundário | E-mail   | ✅          | ❌             | Apenas Parceiro Comercial, máx 1 adicional  |
| Telefone          | Telefone | ✅          | ✅             | Formato (XX) XXXXX-XXXX                     |
| Idioma padrão     | Select   | ✅          | ✅             | Português Brasil (padrão), Inglês, Espanhol |

Seção: Integração da Conta (Apenas Parceiro Comercial)

| Campo            | Descrição                                                                                                           |
|------------------|---------------------------------------------------------------------------------------------------------------------|
| Google Analytics | Permite ao Parceiro Comercial conectar sua conta do Google Analytics para monitorar acessos à página de sua atração |
| Status           | "Conectado" ou "Desconectado"                                                                                       |
| Ação             | Botão para conectar/desconectar                                                                                     |

Regras de Negócio

| ID        | Regra                                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------------------|
| RN-005.01 | O campo  **E-mail principal**  (primeiro e-mail cadastrado) não pode ser alterado pelo usuário                 |
| RN-005.02 | O campo  **CPF/CNPJ**  não pode ser alterado pelo usuário (somente via Gestão de Usuários)                     |
| RN-005.03 | O campo  **Perfil**  não pode ser alterado pelo usuário (somente via Gestão de Usuários)                       |
| RN-005.04 | O usuário  **não pode**  alterar ou resetar sua senha por este modal - deve solicitar ao suporte da plataforma |
| RN-005.05 | A foto deve ter tamanho máximo de  **5MB**  e formatos aceitos: PNG, JPEG                                      |
| RN-005.06 | Ao clicar em "Apagar" na foto, o sistema remove a foto atual e exibe o avatar padrão                           |
| RN-005.07 | O telefone deve ser validado no formato brasileiro: (XX) XXXXX-XXXX                                            |
| RN-005.08 | O  **Idioma padrão**  afeta a interface do backoffice E os e-mails enviados ao usuário                         |
| RN-005.09 | O idioma padrão é  **Português Brasil**  para novos usuários                                                   |
| RN-005.10 | Apenas o perfil  **Parceiro Comercial**  pode adicionar e-mail secundário                                      |
| RN-005.11 | O limite máximo de e-mails é  **2**  (1 principal + 1 secundário)                                              |
| RN-005.12 | Apenas o perfil  **Parceiro Comercial**  visualiza a seção "Integração da conta"                               |
| RN-005.13 | A integração com Google Analytics permite ao Parceiro Comercial monitorar acessos à página de sua atração      |

Critérios de Aceitação

| ID        | Critério                                       | Resultado Esperado                                                        |
|-----------|------------------------------------------------|---------------------------------------------------------------------------|
| CA-005.01 | Clicar em "Perfil" no menu                     | Modal de perfil é aberto                                                  |
| CA-005.02 | Visualizar dados do perfil                     | Campos exibem dados corretos do usuário logado                            |
| CA-005.03 | Editar Primeiro nome e Último nome             | Campos são editáveis e salvos corretamente                                |
| CA-005.04 | Tentar editar CPF/CNPJ                         | Campo é exibido como somente leitura                                      |
| CA-005.05 | Tentar editar e-mail principal                 | Campo é exibido como somente leitura                                      |
| CA-005.06 | Fazer upload de foto válida (PNG, 3MB)         | Foto é carregada e exibida                                                |
| CA-005.07 | Fazer upload de foto > 5MB                     | Mensagem "Arquivo excede o tamanho máximo de 5MB"                         |
| CA-005.08 | Fazer upload de arquivo não suportado (PDF)    | Mensagem "Formato não suportado. Use PNG ou JPEG"                         |
| CA-005.09 | Clicar em "Apagar" na foto                     | Foto removida, avatar padrão exibido                                      |
| CA-005.10 | Alterar idioma para "Inglês"                   | Interface atualiza para inglês após salvar                                |
| CA-005.11 | Clicar em "Sair"                               | Modal fechado, alterações descartadas                                     |
| CA-005.12 | Clicar em "Salvar" com dados válidos           | Dados salvos + mensagem "Perfil atualizado com sucesso"                   |
| CA-005.13 | Acessar perfil como  **Parceiro Comercial**    | Seções "Adicionar outro email" e "Integração da conta" visíveis           |
| CA-005.14 | Acessar perfil como  **Administrador**         | Seções "Adicionar outro email" e "Integração da conta"  **não**  visíveis |
| CA-005.15 | Parceiro Comercial adiciona e-mail secundário  | E-mail adicionado com sucesso (limite 2)                                  |
| CA-005.16 | Parceiro Comercial tenta adicionar 3º e-mail   | Botão "Adicionar outro email" desabilitado/oculto                         |
| CA-005.17 | Parceiro Comercial conecta Google Analytics    | Status muda para "Conectado"                                              |
| CA-005.18 | Parceiro Comercial desconecta Google Analytics | Status muda para "Desconectado"                                           |

Protótipo/Wireframe

Figura  - WF-004 - Perfil

### 3.6 Gestão de Usuários - Administrador

**ID:** RF-006

Módulo: Gestão de Usuários

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador gerencie os usuários do sistema, incluindo listagem, busca, filtros, visualização, cadastro, edição, inativação, ativação e exclusão de usuários, definindo seus perfis de acesso e dados de contato.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-006.01 | O sistema deve exibir o título "Gestão de Usuários" com subtítulo "Gerencie os usuários do sistema" |
| RF-006.02 | O sistema deve exibir campo de pesquisa por texto (busca por ID, nome ou e-mail)                    |
| RF-006.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                         |
| RF-006.04 | O sistema deve exibir botão "Adicionar usuário" para cadastrar novo usuário                         |
| RF-006.05 | O sistema deve exibir abas para filtrar por status: "Ativos", "Inativos", "Todos"                   |
| RF-006.06 | O sistema deve exibir a aba "Ativos" selecionada por padrão                                         |

Tabela de Usuários

| ID        | Requisito                                                                                                           |
|-----------|---------------------------------------------------------------------------------------------------------------------|
| RF-006.07 | O sistema deve exibir tabela com os usuários cadastrados conforme a aba selecionada                                 |
| RF-006.08 | A tabela deve exibir as colunas: Checkbox, User ID, Nome (com foto e e-mail), Perfil, Data de criação, Último login |
| RF-006.09 | Cada coluna deve exibir ícone de ordenação (ASC/DESC)                                                               |
| RF-006.10 | A ordenação padrão deve ser por User ID decrescente (mais recente primeiro)                                         |
| RF-006.11 | A coluna Nome deve exibir: foto do usuário (ou avatar padrão), nome completo e e-mail                               |
| RF-006.12 | A coluna Perfil deve exibir badge visual com o nome do perfil                                                       |
| RF-006.13 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir modal de visualização                      |

Seleção e Ações em Massa

| ID        | Requisito                                                                                             |
|-----------|-------------------------------------------------------------------------------------------------------|
| RF-006.14 | O sistema deve exibir checkbox na primeira coluna para seleção de usuários                            |
| RF-006.15 | O sistema deve permitir selecionar múltiplos usuários via checkbox                                    |
| RF-006.16 | Ao selecionar um ou mais usuários, o sistema deve exibir barra de ações com contador "Selecionados X" |
| RF-006.17 | Na aba "Ativos", a barra de ações deve exibir: "Editar", "Excluir", "Inativar selecionados"           |
| RF-006.18 | Na aba "Inativos", a barra de ações deve exibir: "Editar", "Excluir", "Ativar selecionados"           |
| RF-006.19 | O botão "Editar" deve estar habilitado apenas quando  **1 usuário**  estiver selecionado              |
| RF-006.20 | Os botões "Excluir", "Inativar" e "Ativar" devem funcionar para múltiplos usuários selecionados       |

Paginação

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-006.21 | O sistema deve exibir paginação com seletor de quantidade por página: 10 (padrão), 20, 50, 100   |
| RF-006.22 | O sistema deve exibir indicador de registros: "X a Y de Z"                                       |
| RF-006.23 | O sistema deve exibir navegação: primeira página, anterior, página atual, próxima, última página |

Colunas da Tabela

| Coluna          | Conteúdo                 | Ordenável   | Observação                              |
|-----------------|--------------------------|-------------|-----------------------------------------|
| Checkbox        | ☐                        | ❌           | Seleção múltipla                        |
| User ID         | ID numérico              | ✅           | Ordenação padrão DESC                   |
| Nome            | Foto + Nome + E-mail     | ✅           | Ordena por nome                         |
| Perfil          | Badge com nome do perfil | ✅           | Administrador, Parceiro Comercial, etc. |
| Data de criação | DD/MM/AAAA HH:MM:SS      | ✅           | Data de cadastro                        |
| Último login    | DD/MM/AAAA HH:MM:SS      | ✅           | Última autenticação                     |

Abas de Status

| Aba      | Descrição                            | Ações Disponíveis                |
|----------|--------------------------------------|----------------------------------|
| Ativos   | Usuários com status ativo            | Editar, Excluir, Inativar        |
| Inativos | Usuários com status inativo          | Editar, Excluir, Ativar          |
| Todos    | Todos os usuários (exceto excluídos) | Editar, Excluir, Inativar/Ativar |

Filtros Avançados (Botão Filtro)

| Filtro          | Tipo               | Opções                                                             |
|-----------------|--------------------|--------------------------------------------------------------------|
| Perfil          | Multi-select       | Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente |
| Data de criação | Intervalo de datas | Data inicial - Data final                                          |
| Último login    | Intervalo de datas | Data inicial - Data final                                          |
| Nunca logou     | Checkbox           | Usuários que nunca fizeram login                                   |

Ações Detalhadas

Visualizar (Clicar na linha)

| ID        | Requisito                                                                        |
|-----------|----------------------------------------------------------------------------------|
| RF-006.24 | Ao clicar em uma linha da tabela, o sistema deve abrir modal de visualização     |
| RF-006.25 | O modal de visualização deve exibir todos os campos do usuário (conforme RF-007) |
| RF-006.26 | Todos os campos devem estar  **desabilitados para edição**  (somente leitura)    |
| RF-006.27 | O modal deve exibir botão "Fechar" para retornar à listagem                      |

Editar (Via seleção)

| ID        | Requisito                                                                     |
|-----------|-------------------------------------------------------------------------------|
| RF-006.28 | O botão "Editar" deve estar habilitado apenas com  **1 usuário selecionado**  |
| RF-006.29 | Ao clicar em "Editar", o sistema deve abrir modal de edição (conforme RF-007) |
| RF-006.30 | O modal de edição deve permitir alteração dos campos editáveis                |

Excluir

| ID        | Requisito                                                                               |
|-----------|-----------------------------------------------------------------------------------------|
| RF-006.31 | Ao clicar em "Excluir", o sistema deve exibir modal de confirmação                      |
| RF-006.32 | O modal deve informar a quantidade de usuários que serão excluídos                      |
| RF-006.33 | Ao confirmar, o sistema deve realizar  **soft delete**  (marcar como excluído no banco) |
| RF-006.34 | Usuários excluídos  **não devem**  aparecer em nenhuma aba da listagem                  |
| RF-006.35 | O sistema deve exibir mensagem de sucesso após exclusão                                 |

Inativar

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-006.36 | Ao clicar em "Inativar selecionados", o sistema deve exibir modal de confirmação       |
| RF-006.37 | Ao confirmar, o sistema deve alterar o status dos usuários para "Inativo"              |
| RF-006.38 | Usuários inativados devem aparecer na aba "Inativos"                                   |
| RF-006.39 | O sistema deve exibir mensagem de sucesso informando quantos usuários foram inativados |

Ativar (Aba Inativos)

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-006.40 | Na aba "Inativos", ao selecionar usuários, exibir botão "Ativar selecionados"        |
| RF-006.41 | Ao clicar em "Ativar selecionados", o sistema deve exibir modal de confirmação       |
| RF-006.42 | Ao confirmar, o sistema deve alterar o status dos usuários para "Ativo"              |
| RF-006.43 | Usuários ativados devem aparecer na aba "Ativos"                                     |
| RF-006.44 | O sistema deve exibir mensagem de sucesso informando quantos usuários foram ativados |

Regras de Negócio

| ID        | Regra                                                                                                 |
|-----------|-------------------------------------------------------------------------------------------------------|
| RN-006.01 | Apenas o perfil  **Administrador**  tem acesso a este módulo                                          |
| RN-006.02 | O Administrador  **não pode**  inativar ou excluir a si mesmo                                         |
| RN-006.03 | Ao inativar um usuário, sua sessão ativa deve ser encerrada imediatamente                             |
| RN-006.04 | Usuários inativos  **não podem**  fazer login nem ser utilizados em outras rotinas do sistema         |
| RN-006.05 | Usuários inativos  **podem**  ser reativados pelo Administrador via aba "Inativos"                    |
| RN-006.06 | A exclusão é um  **soft delete**  - o registro é marcado como excluído no banco de dados              |
| RN-006.07 | Usuários excluídos  **não podem**  ser recuperados pelo Administrador (apenas equipe de TI via banco) |
| RN-006.08 | Usuários excluídos  **não aparecem**  em nenhuma listagem do sistema                                  |
| RN-006.09 | O botão "Editar" só é habilitado quando  **exatamente 1 usuário**  está selecionado                   |
| RN-006.10 | A pesquisa deve buscar em: User ID, Nome e E-mail (case insensitive)                                  |
| RN-006.11 | A ordenação padrão é por  **User ID decrescente**  (mais recente primeiro)                            |
| RN-006.12 | A paginação padrão exibe  **10 registros**  por página                                                |
| RN-006.13 | Usuários que nunca logaram devem exibir "-" ou "Nunca" na coluna "Último login"                       |
| RN-006.14 | A senha do usuário  **não deve**  ser exibida em nenhuma tela (segurança)                             |

Barra de Ações por Aba

| Aba      | Ações                                                               |
|----------|---------------------------------------------------------------------|
| Ativos   | [Selecionados X] [Editar] [Excluir] [Inativar selecionados]         |
| Inativos | [Selecionados X] [Editar] [Excluir] [Ativar selecionados]           |
| Todos    | [Selecionados X] [Editar] [Excluir] [Inativar/Ativar selecionados]* |

O botão muda conforme o status dos usuários selecionados

Critérios de Aceitação

| ID        | Critério                                         | Resultado Esperado                                                     |
|-----------|--------------------------------------------------|------------------------------------------------------------------------|
| CA-006.01 | Acessar Gestão de Usuários como Administrador    | Tela exibida com aba "Ativos" selecionada                              |
| CA-006.02 | Visualizar lista de usuários                     | Tabela exibe usuários ativos com todas as colunas                      |
| CA-006.03 | Pesquisar por nome "João"                        | Lista filtrada exibindo usuários com "João" no nome                    |
| CA-006.04 | Pesquisar por e-mail "@gmail"                    | Lista filtrada exibindo usuários com "@gmail" no e-mail                |
| CA-006.05 | Clicar em "Filtro"                               | Modal/dropdown de filtros avançados é exibido                          |
| CA-006.06 | Filtrar por perfil "Editor"                      | Lista exibe apenas usuários com perfil Editor                          |
| CA-006.07 | Clicar na aba "Inativos"                         | Lista atualiza exibindo apenas usuários inativos                       |
| CA-006.08 | Clicar na aba "Todos"                            | Lista atualiza exibindo usuários ativos e inativos                     |
| CA-006.09 | Clicar em uma linha da tabela                    | Modal de visualização abre com campos desabilitados                    |
| CA-006.10 | Selecionar 1 usuário via checkbox                | Barra de ações exibe: "Selecionados 1", Editar, Excluir, Inativar      |
| CA-006.11 | Selecionar 3 usuários via checkbox               | Barra de ações exibe: "Selecionados 3", botão Editar  **desabilitado** |
| CA-006.12 | Clicar em "Editar" com 1 usuário selecionado     | Modal de edição abre com campos habilitados                            |
| CA-006.13 | Clicar em "Excluir" com usuários selecionados    | Modal de confirmação exibe quantidade a ser excluída                   |
| CA-006.14 | Confirmar exclusão                               | Usuários removidos da lista + mensagem de sucesso                      |
| CA-006.15 | Verificar usuário excluído                       | Usuário não aparece em nenhuma aba (Ativos, Inativos, Todos)           |
| CA-006.16 | Clicar em "Inativar selecionados"                | Modal de confirmação é exibido                                         |
| CA-006.17 | Confirmar inativação                             | Usuários movidos para aba "Inativos" + mensagem de sucesso             |
| CA-006.18 | Na aba Inativos, clicar em "Ativar selecionados" | Modal de confirmação é exibido                                         |
| CA-006.19 | Confirmar ativação                               | Usuários movidos para aba "Ativos" + mensagem de sucesso               |
| CA-006.20 | Tentar inativar a si mesmo                       | Mensagem "Não é possível inativar seu próprio usuário"                 |
| CA-006.21 | Tentar excluir a si mesmo                        | Mensagem "Não é possível excluir seu próprio usuário"                  |
| CA-006.22 | Ordenar por "Nome" ascendente                    | Lista reordenada de A-Z                                                |
| CA-006.23 | Alterar paginação para 50                        | Lista exibe até 50 registros por página                                |
| CA-006.24 | Navegar para próxima página                      | Lista exibe próximos registros                                         |
| CA-006.25 | Clicar em "Adicionar usuário"                    | Modal de cadastro é aberto (RF-007)                                    |

Protótipo/Wireframe

Figura  - WF-005 - Gestão de Usuários.png

### 3.7 Cadastro de Usuários - Administrador

**ID:** RF-007

Módulo: Gestão de Usuários &gt; Cadastro/Edição

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador cadastre novos usuários ou edite/visualize usuários existentes através de um modal. Os campos exibidos variam dinamicamente conforme o perfil selecionado. O mesmo modal é utilizado para as três ações: Novo, Editar e Visualizar.

**Requisitos Detalhados**

**Estrutura Geral do Modal**

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-007.01 | O sistema deve exibir modal com título "Novo/Editar Usuário"                                |
| RF-007.02 | O sistema deve exibir subtítulo "Preencha os campos obrigatórios para adicionar um usuário" |
| RF-007.03 | O sistema deve exibir botões "Descartar" e "Salvar" no cabeçalho                            |
| RF-007.04 | O sistema deve validar campos obrigatórios antes de salvar                                  |
| RF-007.05 | O sistema deve exibir campos específicos dinamicamente conforme o perfil selecionado        |

**Modos de Operação**

| Modo         | Descrição                      | Campos de Senha                     | Data Criação   | Último Acesso   | Campos        |
|--------------|--------------------------------|-------------------------------------|----------------|-----------------|---------------|
| Novo         | Cadastro de novo usuário       | ❌ Oculto                            | Data atual     | Em branco ("-") | Habilitados   |
| Edição       | Alteração de usuário existente | ✅ Visível (criptografado + Resetar) | Preenchido     | Preenchido      | Habilitados   |
| Visualização | Consulta de usuário            | ✅ Visível (criptografado)           | Preenchido     | Preenchido      | Desabilitados |

**Campos Comuns (Todos os Perfis)**

| Campo               | Tipo      | Obrigatório   | Editável   | Observação                                                                  |
|---------------------|-----------|---------------|------------|-----------------------------------------------------------------------------|
| Foto de Perfil      | Upload    | ❌             | ✅          | PNG, JPEG - máx 5MB                                                         |
| Primeiro nome       | Texto     | ✅             | ✅          | Máximo 50 caracteres                                                        |
| Último nome         | Texto     | ✅             | ✅          | Máximo 50 caracteres                                                        |
| CPF/CNPJ            | Texto     | ❌             | ✅          | Máscara automática                                                          |
| Email de contato    | E-mail    | ✅             | ✅          | Permite adicionar outro email (máx 2)                                       |
| Telefone            | Telefone  | ✅             | ✅          | Formato (XX) XXXXX-XXXX                                                     |
| Idioma padrão       | Select    | ✅             | ✅          | Português Brasil (padrão), Inglês, Espanhol                                 |
| Senha               | Password  | -             | ❌          | Apenas visualização (criptografado) - só no modo Edição/Visualização        |
| Botão Resetar Senha | Botão     | -             | -          | Apenas no modo Edição                                                       |
| Data de criação     | Data/Hora | -             | ❌          | Somente leitura - Data atual no modo Novo                                   |
| Último acesso       | Data/Hora | -             | ❌          | Somente leitura - Em branco ("-") no modo Novo                              |
| Perfil              | Select    | ✅             | ✅          | Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente, Turista |
| Ativo               | Toggle    | ✅             | ✅          | Ativar/desativar o usuário                                                  |

**Campos Específicos por Perfil**

**Perfil: Parceiro Comercial**

| Seção            | Campo              | Tipo           | Obrigatório   | Observação                                              |
|------------------|--------------------|----------------|---------------|---------------------------------------------------------|
| Gestor           | Nome               | Texto          | ✅             | Primeiro nome do gestor                                 |
| Gestor           | Último nome        | Texto          | ✅             | Último nome do gestor                                   |
| Gestor           | Email do Gestor    | E-mail         | ✅             | Permite adicionar outro email (máx 2)                   |
| Gestor           | Telefone do Gestor | Telefone       | ✅             | Formato (XX) XXXXX-XXXX                                 |
| Dados da empresa | Razão Social       | Texto          | ✅             | Nome legal da empresa                                   |
| Dados da empresa | Nome Fantasia      | Texto          | ✅             | Nome comercial                                          |
| Dados da empresa | CNPJ               | Texto          | ✅             | Máscara  [XX.XXX.XXX/XXXX-XX](http:/XX.XXX.XXX/XXXX-XX) |
| Dados da empresa | Inscrição Estadual | Texto + Toggle | ✅             | Campo texto OU marcar "Isento"                          |
| Integração       | Google Analytics   | Botão          | ❌             | Conectar/Desconectar conta do GA                        |

**Perfil: Editor / Leitor**

| Campo              | Tipo                      | Obrigatório   | Observação                                                                                       |
|--------------------|---------------------------|---------------|--------------------------------------------------------------------------------------------------|
| Parceiro Comercial | Select com pesquisa       | ✅             | Pesquisa por nome do Parceiro Comercial                                                          |
| Atração            | Multi-select com pesquisa | ✅             | Exibe atrações ativas do Parceiro selecionado. Pesquisa por nome ou ID. Permite múltipla seleção |

**Perfil: Agência**

| Campo              | Tipo                      | Obrigatório   | Observação                                                             |
|--------------------|---------------------------|---------------|------------------------------------------------------------------------|
| Visibilidade       | Select                    | ✅             | Opções: "Pública" ou "Reservada"                                       |
| Parceiro Comercial | Multi-select com pesquisa | Condicional   | Visível apenas se Visibilidade = "Reservada". Permite múltipla seleção |
| Atração            | Multi-select com pesquisa | ❌             | Permite vincular a múltiplas atrações. Pesquisa por nome ou ID         |

**Perfil: Agente**

| Campo   | Tipo                | Obrigatório   | Observação                                                                |
|---------|---------------------|---------------|---------------------------------------------------------------------------|
| Agência | Select com pesquisa | ❌             | Pesquisa por nome ou ID da agência. Pode ser independente (não vinculado) |

**Perfil: Turista**

| Campo       | Tipo   | Obrigatório   | Observação                                  |
|-------------|--------|---------------|---------------------------------------------|
| Estrangeiro | Toggle | ✅             | Sim/Não - Indica se o turista é estrangeiro |

**Regras de Negócio**

| ID        | Regra                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------|
| RN-007.01 | O campo ID é gerado automaticamente de forma incremental ao salvar                               |
| RN-007.02 | O ID só é exibido na tela de Gestão de Usuários após salvar (não aparece no modal de cadastro)   |
| RN-007.03 | Ao cadastrar novo usuário, o sistema gera senha provisória automaticamente                       |
| RN-007.04 | A senha provisória é enviada via e-mail E SMS para o usuário                                     |
| RN-007.05 | O botão "Resetar senha" gera nova senha provisória e envia por e-mail e SMS                      |
| RN-007.06 | O Administrador não pode definir ou visualizar a senha do usuário (apenas resetar)               |
| RN-007.07 | A foto de perfil deve ter tamanho máximo de 5MB e formatos PNG ou JPEG                           |
| RN-007.08 | O e-mail principal (primeiro cadastrado) é usado para login e não pode ser alterado após criação |
| RN-007.09 | O limite máximo de e-mails é 2 (1 principal + 1 secundário)                                      |
| RN-007.10 | O campo Idioma padrão define o idioma da interface E dos e-mails enviados ao usuário             |
| RN-007.11 | Para Editor/Leitor: o campo "Atração" só exibe atrações ativas do Parceiro Comercial selecionado |
| RN-007.12 | Para Agência Pública: pode ser vinculada a múltiplos Parceiros Comerciais e Atrações             |
| RN-007.13 | Para Agência Reservada: o campo "Parceiro Comercial" é obrigatório e visível                     |
| RN-007.14 | Para Agente: o campo "Agência" permite pesquisa por nome ou ID                                   |
| RN-007.15 | O perfil Turista pode ser cadastrado pelo Admin ou via auto-cadastro no portal público           |
| RN-007.16 | No modo Visualização, todos os campos devem estar desabilitados (somente leitura)                |
| RN-007.17 | O campo "Data de criação" exibe a data atual automaticamente no cadastro de novo usuário         |
| RN-007.18 | O campo "Último acesso" exibe "-" (em branco) para usuários que nunca logaram                    |
| RN-007.19 | Campos de Gestor, Dados da empresa e Integração são exclusivos do perfil Parceiro Comercial      |

**Validações**

| Campo              | Validação                                                        |
|--------------------|------------------------------------------------------------------|
| E-mail             | Formato válido, único no sistema (case insensitive)              |
| Telefone           | Formato brasileiro (XX) XXXXX-XXXX                               |
| CPF                | 11 dígitos, validação de dígitos verificadores                   |
| CNPJ               | 14 dígitos, validação de dígitos verificadores, único no sistema |
| Foto               | Máximo 5MB, formatos PNG ou JPEG                                 |
| Inscrição Estadual | Texto ou marcado como "Isento"                                   |

Critérios de Aceitação

**Modo Novo (Cadastro)**

| ID        | Critério                                            | Resultado Esperado                                          |
|-----------|-----------------------------------------------------|-------------------------------------------------------------|
| CA-007.01 | Clicar em "Adicionar usuário" na Gestão de Usuários | Modal abre em modo Novo                                     |
| CA-007.02 | Verificar seção de Senha no modo Novo               | Seção de senha não aparece                                  |
| CA-007.03 | Verificar Data de criação                           | Exibe data/hora atual                                       |
| CA-007.04 | Verificar Último acesso                             | Exibe "-" (em branco)                                       |
| CA-007.05 | Preencher campos obrigatórios e salvar              | Usuário criado + e-mail e SMS enviados com senha provisória |
| CA-007.06 | Verificar ID após salvar                            | ID não aparece no modal, mas aparece na listagem            |

**Modo Edição**

| ID        | Critério                                | Resultado Esperado                                  |
|-----------|-----------------------------------------|-----------------------------------------------------|
| CA-007.07 | Selecionar usuário e clicar em "Editar" | Modal abre em modo Edição com campos habilitados    |
| CA-007.08 | Verificar seção de Senha                | Senha aparece criptografada + botão "Resetar senha" |
| CA-007.09 | Clicar em "Resetar senha"               | Confirmação + nova senha enviada por e-mail e SMS   |
| CA-007.10 | Alterar dados e salvar                  | Dados atualizados + mensagem de sucesso             |

**Modo Visualização**

| ID        | Critério                                    | Resultado Esperado                              |
|-----------|---------------------------------------------|-------------------------------------------------|
| CA-007.11 | Clicar em linha da tabela (não no checkbox) | Modal abre em modo Visualização                 |
| CA-007.12 | Verificar campos                            | Todos os campos desabilitados (somente leitura) |
| CA-007.13 | Verificar botão "Resetar senha"             | Botão não aparece no modo visualização          |

**Campos Dinâmicos por Perfil**

| ID        | Critério                                      | Resultado Esperado                                    |
|-----------|-----------------------------------------------|-------------------------------------------------------|
| CA-007.14 | Selecionar perfil "Administrador"             | Apenas campos comuns são exibidos                     |
| CA-007.15 | Selecionar perfil "Parceiro Comercial"        | Seções Gestor, Dados da empresa e Integração aparecem |
| CA-007.16 | Selecionar perfil "Editor" ou "Leitor"        | Campos Parceiro Comercial e Atração aparecem          |
| CA-007.17 | Selecionar Parceiro Comercial (Editor/Leitor) | Campo Atração exibe apenas atrações deste Parceiro    |
| CA-007.18 | Selecionar perfil "Agência"                   | Campos Visibilidade e Atração aparecem                |
| CA-007.19 | Selecionar Visibilidade "Reservada" (Agência) | Campo Parceiro Comercial aparece                      |
| CA-007.20 | Selecionar Visibilidade "Pública" (Agência)   | Campo Parceiro Comercial não aparece                  |
| CA-007.21 | Selecionar perfil "Agente"                    | Campo Agência aparece                                 |
| CA-007.22 | Selecionar perfil "Turista"                   | Campo Estrangeiro aparece                             |

**Validações**

| ID        | Critério                                 | Resultado Esperado                                |
|-----------|------------------------------------------|---------------------------------------------------|
| CA-007.23 | Salvar sem preencher campos obrigatórios | Mensagem de erro indicando campos faltantes       |
| CA-007.24 | Cadastrar e-mail já existente            | Mensagem "E-mail já cadastrado no sistema"        |
| CA-007.25 | Cadastrar CNPJ já existente              | Mensagem "CNPJ já cadastrado no sistema"          |
| CA-007.26 | Upload de foto > 5MB                     | Mensagem "Arquivo excede o tamanho máximo de 5MB" |
| CA-007.27 | Upload de arquivo não suportado          | Mensagem "Formato não suportado. Use PNG ou JPEG" |

**Protótipo/Wireframe**

Figura  - WF-006 - Adicionar Usuários.png

### 3.8 Tela Gestão de Contratos - Administrador

**ID:** RF-008

Módulo: Gestão de Contratos

Perfis com Acesso: Administrador (CRUD), Parceiro Comercial (Visualização)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador visualize, gerencie e acompanhe os contratos das atrações. Os contratos são agrupados por Parceiro Comercial, permitindo expandir para visualizar os contratos individuais de cada atração. O módulo integra com Docusign para coleta de assinaturas digitais.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-008.01 | O sistema deve exibir título "Gestão de Contratos" com subtítulo "Gerencie os contratos do sistema" |
| RF-008.02 | O sistema deve exibir campo de busca para pesquisa                                                  |
| RF-008.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                         |
| RF-008.04 | O sistema deve exibir botão "Adicionar Contrato"                                                    |
| RF-008.05 | O sistema deve exibir abas para filtrar contratos:  **Ativos**  ,  **Inativos**  ,  **Todos**       |

Tipos de Contrato

| Tipo de Contrato    | Usuário Vinculado   | Descrição                                                   |
|---------------------|---------------------|-------------------------------------------------------------|
| Contrato de Atração | Parceiro Comercial  | Contrato para exploração comercial de uma atração turística |
| Contrato de Agência | Agência             | Contrato para divulgação da plataforma e atrações           |

Tabela Principal (Parceiros Comerciais)

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-008.06 | O sistema deve exibir lista de  **Parceiros Comerciais e Agências**  que possuem contratos |
| RF-008.07 | O sistema deve exibir ícone de expansão (seta) em cada linha de Parceiro                   |
| RF-008.08 | Ao clicar na linha ou seta, o sistema deve expandir e exibir os contratos do Parceiro      |

Colunas da Tabela Principal:

| Coluna                  | Descrição                           | Ordenável   |
|-------------------------|-------------------------------------|-------------|
| Ícone de expansão       | Seta para expandir/recolher         | ❌           |
| ID Parceiro/Agência     | ID do Parceiro Comercial ou Agência | ✅           |
| Nome Parceiro Comercial | Nome do Parceiro (com foto/avatar)  | ✅           |
| Tipo                    | Parceiro Comercial / Agência        |             |

Tabela Expandida (Contratos)

| ID        | Requisito                                                                       |
|-----------|---------------------------------------------------------------------------------|
| RF-008.09 | O sistema deve exibir tabela com os contratos do Parceiro Comercial selecionado |
| RF-008.10 | O sistema deve exibir checkbox em cada linha para seleção múltipla              |
| RF-008.11 | Cada contrato está vinculado a uma atração específica                           |

Colunas da Tabela de Contratos:

| Coluna         | Descrição                                 | Ordenável   |
|----------------|-------------------------------------------|-------------|
| Checkbox       | Seleção do contrato                       | ❌           |
| Contrato ID    | Identificador único do contrato           | ✅           |
| Nome Atração   | Nome da atração vinculada ao contrato     | ✅           |
| Status         | Status atual do contrato (badge colorido) | ✅           |
| Data Expiração | Data de expiração do contrato             | ✅           |

Status do Contrato

| Status             | Descrição                                          | Cor Sugerida   | Transição            |
|--------------------|----------------------------------------------------|----------------|----------------------|
| Rascunho           | Contrato em preenchimento                          | 🔘 Cinza        | → Aguardando Envio   |
| Aguardando Envio   | Contrato totalmente preenchido, pronto para enviar | 🟡 Amarelo      | → Enviado a Docusign |
| Enviado a Docusign | Aguardando assinaturas na plataforma Docusign      | 🔵 Azul         | → Ativo              |
| Ativo              | Contrato assinado e vigente                        | 🟢 Verde        | → Expirado / Inativo |
| Expirado           | Data de expiração atingida (automático)            | 🟠 Laranja      | -                    |
| Inativo            | Cancelado ou desativado manualmente                | ⚫ Cinza escuro | -                    |

Barra de Ações (ao selecionar contratos)

| ID        | Requisito                                                                                      |
|-----------|------------------------------------------------------------------------------------------------|
| RF-008.12 | O sistema deve exibir contador "Selecionados X" indicando quantidade de contratos selecionados |
| RF-008.13 | O sistema deve exibir barra de ações quando houver pelo menos 1 contrato selecionado           |

Ações Disponíveis:

| Ação                  | Seleção    | Descrição                                  |
|-----------------------|------------|--------------------------------------------|
| Enviar Docusign       | Múltiplos* | Envia contratos para coleta de assinaturas |
| Download PDF          | Múltiplos  | Baixa o PDF do contrato preenchido         |
| Editar                | Apenas 1   | Abre tela de edição (RF-009)               |
| Excluir               | Múltiplos  | Exclui contratos (soft delete)             |
| Inativar selecionados | Múltiplos  | Muda status para "Inativo"                 |

*Nota: Envio em massa para Docusign sujeito a limitações da integração (a confirmar com equipe técnica)*

Funcionalidades de Busca e Filtro

Campo de Busca

| ID        | Requisito                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| RF-008.14 | O sistema deve permitir busca por texto livre                                                        |
| RF-008.15 | A busca deve pesquisar nos campos: ID do Parceiro, Nome do Parceiro, ID do Contrato, Nome da Atração |
| RF-008.16 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                            |

Filtros Avançados

| Filtro             | Tipo             | Opções                                                                   |
|--------------------|------------------|--------------------------------------------------------------------------|
| Status             | Multi-select     | Rascunho, Aguardando Envio, Enviado a Docusign, Ativo, Expirado, Inativo |
| Data de Expiração  | Range de datas   | De / Até                                                                 |
| Parceiro Comercial | Select com busca | Lista de Parceiros                                                       |
| Atração            | Select com busca | Lista de Atrações                                                        |
| Tipo de Contrato   | Select           | Parceiro Comercial, Agência, Todos                                       |

Paginação

| ID        | Requisito                                                                                 |
|-----------|-------------------------------------------------------------------------------------------|
| RF-008.17 | O sistema deve carregar por padrão  **10 Parceiros Comerciais**  por página               |
| RF-008.18 | O sistema deve permitir alterar para exibir 10, 20, 50 ou 100 registros                   |
| RF-008.19 | O sistema deve exibir navegação: primeira página, anterior, "X a Y de Z", próxima, última |

Regras de Negócio

| ID        | Regra                                                                                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RN-008.01 | Os contratos são  **agrupados por Parceiro Comercial**  na visualização principal                                         |
| RN-008.02 | Cada  **contrato está vinculado a uma única atração**                                                                     |
| RN-008.03 | Um Parceiro Comercial pode ter  **múltiplas atrações**  , cada uma com seu próprio contrato                               |
| RN-008.04 | As abas filtram contratos por status:  **Ativos**  (status Ativo),  **Inativos**  (status Inativo + Expirado),  **Todos** |
| RN-008.05 | Contratos em preenchimento recebem status  **"Rascunho"**                                                                 |
| RN-008.06 | Contratos totalmente preenchidos recebem status  **"Aguardando Envio"**                                                   |
| RN-008.07 | Contratos enviados para Docusign recebem status  **"Enviado a Docusign"**                                                 |
| RN-008.08 | Após confirmação de todas as assinaturas, status muda automaticamente para  **"Ativo"**                                   |
| RN-008.09 | Quando a  **data de expiração**  é atingida, o sistema muda automaticamente o status para  **"Expirado"**                 |
| RN-008.10 | O status  **"Inativo"**  é aplicado por cancelamento ou ação manual do administrador                                      |
| RN-008.11 | A ação  **"Excluir"**  realiza soft delete (marca como excluído no banco, não remove fisicamente)                         |
| RN-008.12 | O botão  **"Editar"**  só é habilitado quando  **apenas 1 contrato**  está selecionado                                    |
| RN-008.13 | O  **Download PDF**  baixa o arquivo do contrato já preenchido com os dados (Razão Social, CNPJ, etc.)                    |
| RN-008.14 | Ao clicar em  **"Enviar Docusign"**  , o sistema abre preview do contrato para revisão antes do envio                     |
| RN-008.15 | Ao clicar em  **"Excluir"**  , o sistema exibe confirmação: "Deseja realmente excluir o(s) contrato(s) selecionado(s)?"   |
| RN-008.16 | A integração com Docusign utiliza a  **conta da plataforma Curitiba 360**                                                 |
| RN-008.17 | Os  **signatários**  do contrato são: Curitiba 360 (plataforma) e o Parceiro Comercial                                    |
| RN-008.18 | Somente contratos com status  **"Aguardando Envio"**  podem ser enviados para Docusign                                    |
| RN-008.19 | Contratos excluídos (soft delete)  **não aparecem**  em nenhuma aba                                                       |
| RN-008.20 | Existem dois tipos de contrato: Contrato de Atração (Parceiro Comercial) e Contrato de Agência                            |
| RN-008.21 | Contratos de Parceiro Comercial são vinculados a uma atração específica                                                   |
| RN-008.22 | Contratos de Agência são vinculados diretamente à agência (sem atração)                                                   |

Critérios de Aceitação

Visualização e Navegação

| ID        | Critério                                 | Resultado Esperado                                       |
|-----------|------------------------------------------|----------------------------------------------------------|
| CA-008.01 | Acessar Gestão de Contratos              | Lista de Parceiros Comerciais com contratos é exibida    |
| CA-008.02 | Clicar na linha de um Parceiro Comercial | Contratos do parceiro são expandidos/exibidos            |
| CA-008.03 | Clicar na seta de expansão               | Contratos são expandidos/recolhidos                      |
| CA-008.04 | Selecionar aba "Ativos"                  | Apenas contratos com status "Ativo" são exibidos         |
| CA-008.05 | Selecionar aba "Inativos"                | Contratos com status "Inativo" e "Expirado" são exibidos |
| CA-008.06 | Selecionar aba "Todos"                   | Todos os contratos são exibidos (exceto excluídos)       |

Busca e Filtros

| ID        | Critério                       | Resultado Esperado                                           |
|-----------|--------------------------------|--------------------------------------------------------------|
| CA-008.07 | Pesquisar por nome do Parceiro | Parceiros que correspondem à busca são exibidos              |
| CA-008.08 | Pesquisar por ID do contrato   | Parceiro com o contrato correspondente é exibido (expandido) |
| CA-008.09 | Filtrar por status             | Apenas contratos com o status selecionado são exibidos       |
| CA-008.10 | Filtrar por data de expiração  | Contratos dentro do período são exibidos                     |

Seleção e Ações

| ID        | Critério                                          | Resultado Esperado                         |
|-----------|---------------------------------------------------|--------------------------------------------|
| CA-008.11 | Selecionar checkbox de um contrato                | Barra de ações aparece com todas as opções |
| CA-008.12 | Selecionar múltiplos contratos                    | Contador "Selecionados X" é atualizado     |
| CA-008.13 | Selecionar 2+ contratos                           | Botão "Editar" fica  **desabilitado**      |
| CA-008.14 | Selecionar apenas 1 contrato e clicar em "Editar" | Sistema abre tela de edição (RF-009)       |

Ações de Contrato

| ID        | Critério                          | Resultado Esperado                                 |
|-----------|-----------------------------------|----------------------------------------------------|
| CA-008.15 | Clicar em "Download PDF"          | Sistema baixa o arquivo PDF do contrato preenchido |
| CA-008.16 | Clicar em "Excluir"               | Modal de confirmação é exibido                     |
| CA-008.17 | Confirmar exclusão                | Contrato é removido da lista (soft delete)         |
| CA-008.18 | Clicar em "Inativar selecionados" | Status dos contratos muda para "Inativo"           |

Integração Docusign

| ID        | Critério                                                             | Resultado Esperado                                                                 |
|-----------|----------------------------------------------------------------------|------------------------------------------------------------------------------------|
| CA-008.19 | Selecionar contrato "Aguardando Envio" e clicar em "Enviar Docusign" | Modal de preview é exibido                                                         |
| CA-008.20 | Confirmar envio no preview                                           | Contrato é enviado para Docusign + status muda para "Enviado a Docusign"           |
| CA-008.21 | Selecionar contrato "Rascunho" e clicar em "Enviar Docusign"         | Mensagem de erro: "Contrato incompleto. Finalize o preenchimento antes de enviar." |
| CA-008.22 | Docusign confirma assinaturas (via webhook)                          | Status do contrato muda automaticamente para "Ativo"                               |

Automações

| ID        | Critério                                            | Resultado Esperado                                  |
|-----------|-----------------------------------------------------|-----------------------------------------------------|
| CA-008.23 | Data de expiração de um contrato "Ativo" é atingida | Sistema muda status automaticamente para "Expirado" |
| CA-008.24 | Verificar contrato expirado na aba "Inativos"       | Contrato expirado aparece na lista                  |

Paginação

| ID        | Critério                             | Resultado Esperado                           |
|-----------|--------------------------------------|----------------------------------------------|
| CA-008.25 | Alterar quantidade para 50 registros | Sistema exibe até 50 Parceiros por página    |
| CA-008.26 | Clicar em "Próxima página"           | Sistema carrega próxima página de resultados |

Protótipo/Wireframe

Figura  - WF-007 - Gestão de Contratos.png

### 3.9 Incluir Contratos - Administrador

**ID:** RF-009

Módulo: Gestão de Contratos &gt; Cadastro/Edição

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador crie e edite contratos. A tela apresenta uma pré-visualização do contrato à esquerda com campos editáveis inline, sincronizados com o painel de preenchimento à direita. O tipo de contrato (template) é carregado automaticamente conforme o perfil do usuário selecionado.

**Requisitos Detalhados**

**Estrutura da Tela**

| ID        | Requisito                                                                                                          |
|-----------|--------------------------------------------------------------------------------------------------------------------|
| RF-009.01 | O sistema deve exibir título "Gestão de Contratos" com subtítulo "Gerencie os contratos do sistema"                |
| RF-009.02 | O sistema deve exibir barra de progresso indicando o percentual de campos preenchidos                              |
| RF-009.03 | O sistema deve exibir botões "Preview" e "Salvar" no cabeçalho                                                     |
| RF-009.04 | O sistema deve dividir a tela em duas colunas: Template do contrato (esquerda) e Painel de preenchimento (direita) |

**Cabeçalho do Formulário**

| Campo               | Tipo             | Obrigatório   | Descrição                                           |
|---------------------|------------------|---------------|-----------------------------------------------------|
| Parceiro ou Agência | Select com busca | ✅             | Seleciona o usuário (Parceiro Comercial ou Agência) |
| ID do contrato      | Somente leitura  | -             | Gerado automaticamente após salvar                  |

**Tipos de Contrato**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.05 | Ao selecionar um usuário Parceiro Comercial, o sistema carrega o template de Contrato de Atração |
| RF-009.06 | Ao selecionar um usuário Agência, o sistema carrega o template de Contrato de Agência            |
| RF-009.07 | Cada tipo de contrato possui um template diferente (fornecido pelo cliente)                      |

| Tipo                | Usuário            | Template                    | Vinculação         |
|---------------------|--------------------|-----------------------------|--------------------|
| Contrato de Atração | Parceiro Comercial | Template Parceiro Comercial | Atração específica |
| Contrato de Agência | Agência            | Template Agência            | Agência            |

Seleção de Atração (apenas para Contrato de Atração)

| ID         | Requisito                                                                                                                                                                  |
|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-009.07A | Após selecionar um Parceiro Comercial, o sistema deve exibir o campo "Selecionar Atração"                                                                                  |
| RF-009.07B | O campo "Selecionar Atração" deve listar apenas atrações do Parceiro selecionado com status "Pendente de Contrato" ou "Rascunho"                                           |
| RF-009.07C | O campo deve ser do tipo select com busca, permitindo pesquisa por ID ou Nome da atração                                                                                   |
| RF-009.07D | Se o Parceiro não tiver atrações disponíveis, exibir mensagem: "Este parceiro não possui atrações disponíveis para vinculação de contrato. Cadastre uma atração primeiro." |
| RF-009.07E | Uma atração só pode ter um contrato ativo por vez. Se já existir contrato ativo para a atração, ela não deve aparecer na lista                                             |
| RF-009.07F | Após a assinatura do contrato no Docusign, a atração vinculada deve ter seu status alterado automaticamente para "Ativo"                                                   |
| RF-009.07G | O campo "Selecionar Atração" NÃO aparece para contratos de Agência (apenas para Contrato de Atração)                                                                       |

**Coluna Esquerda - Template do Contrato**

| ID        | Requisito                                                                                |
|-----------|------------------------------------------------------------------------------------------|
| RF-009.08 | O sistema deve exibir o template fixo do contrato com campos editáveis inline            |
| RF-009.09 | Os campos editáveis são numerados (1, 2, 3...) para facilitar identificação              |
| RF-009.10 | Os campos inline são sincronizados com os campos do painel à direita                     |
| RF-009.11 | Ao preencher um campo no painel direito, o valor é refletido automaticamente no template |
| RF-009.12 | O template é somente leitura (admin não pode editar o texto, apenas os campos)           |

**Coluna Direita - Painel de Preenchimento**

O painel possui duas abas:

**Aba 1: Informações do Contrato**

| ID        | Requisito                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------|
| RF-009.13 | Ao selecionar o Parceiro/Agência, os campos são preenchidos automaticamente com dados do cadastro |
| RF-009.14 | Os campos preenchidos automaticamente são editáveis pelo admin                                    |
| RF-009.15 | Os campos específicos serão definidos quando o cliente fornecer o template                        |

Nota: Os campos definitivos serão documentados após recebimento do template do cliente.

**Aba 2: Condições**

| Seção                   | Descrição                                       |
|-------------------------|-------------------------------------------------|
| Condições Comerciais    | Vincula condições cadastradas no módulo RF 3.10 |
| Informações Financeiras | Define parâmetros de repasse financeiro         |
| Informações Adicionais  | Campo de texto livre                            |

**Seção: Condições Comerciais**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-009.16 | O sistema deve exibir select para escolher Condições Comerciais cadastradas (RF-010) |
| RF-009.17 | O sistema deve permitir criar condições (botão "Criar condição")                     |
| RF-009.18 | O botão "Criar condição" deve abrir o modal de nova condição comercial RF 3.10       |

**Seção: Informações Financeiras**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.19 | O sistema deve permitir criar informações financeiras (botão "Criar informação financeira")      |
| RF-009.20 | O botão " Criar informação financeira " deve abrir o modal de nova informação financeira RF 3.10 |

**Seção: Informações Adicionais**

| ID        | Requisito                                                                               |
|-----------|-----------------------------------------------------------------------------------------|
| RF-009.21 | O sistema deve exibir campo de texto livre para informações adicionais                  |
| RF-009.22 | O conteúdo deste campo é inserido no corpo do contrato ao final dos campos estruturados |

**Barra de Progresso**

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-009.23 | O sistema deve exibir barra de progresso indicando percentual de campos obrigatórios preenchidos |
| RF-009.24 | A barra deve atualizar em tempo real conforme os campos são preenchidos                          |
| RF-009.25 | O sistema deve indicar visualmente quando todos os campos obrigatórios estão preenchidos (100%)  |

**Funcionalidades dos Botões**

**Botão Preview**

| ID        | Requisito                                                                      |
|-----------|--------------------------------------------------------------------------------|
| RF-009.26 | Ao clicar em "Preview", o sistema gera e baixa o PDF do contrato               |
| RF-009.27 | O PDF é gerado com as informações preenchidas até o momento (mesmo incompleto) |
| RF-009.28 | Campos não preenchidos aparecem em branco ou com placeholder no PDF            |

**Botão Salvar**

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-009.29 | Ao clicar em "Salvar", o sistema verifica se todos os campos obrigatórios estão preenchidos |
| RF-009.30 | Se incompleto: exibe modal de confirmação (ver fluxo abaixo)                                |
| RF-009.31 | Se completo: salva com status "Aguardando Envio"                                            |

**Modos de Operação**

| Modo         | Descrição                 | Campos        | Botões          | Origem                                    |
|--------------|---------------------------|---------------|-----------------|-------------------------------------------|
| Novo         | Criar novo contrato       | Habilitados   | Preview, Salvar | Botão "Adicionar Contrato" (RF-008)       |
| Edição       | Editar contrato existente | Habilitados   | Preview, Salvar | Selecionar 1 contrato + "Editar" (RF-008) |
| Visualização | Consultar contrato        | Desabilitados | Preview         | Clicar na linha do contrato (RF-008)      |

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-009.32 | No modo Visualização, todos os campos devem estar desabilitados (somente leitura)           |
| RF-009.33 | No modo Visualização, o botão "Salvar" não é exibido                                        |
| RF-009.34 | Contratos com status "Ativo", "Enviado a Docusign" ou "Expirado" abrem em modo Visualização |
| RF-009.35 | Contratos com status "Rascunho" ou "Aguardando Envio" abrem em modo Edição                  |

**Regras de Negócio**

| ID        | Regra                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------|
| RN-009.01 | O ID do contrato é gerado automaticamente de forma incremental ao salvar                         |
| RN-009.02 | O ID só é exibido após o primeiro salvamento                                                     |
| RN-009.03 | O template do contrato é fixo e fornecido pelo cliente (admin não pode editar o texto)           |
| RN-009.04 | Ao selecionar Parceiro Comercial, carrega template de Contrato de Atração                        |
| RN-009.05 | Ao selecionar Agência, carrega template de Contrato de Agência                                   |
| RN-009.06 | Campos do cadastro (Razão Social, CNPJ, Endereço) são preenchidos automaticamente, mas editáveis |
| RN-009.07 | Os campos inline no template são sincronizados com o painel de preenchimento                     |
| RN-009.08 | A barra de progresso calcula: (campos preenchidos / campos obrigatórios) × 100%                  |
| RN-009.09 | Contrato salvo com campos faltantes recebe status "Rascunho"                                     |
| RN-009.10 | Contrato salvo com todos os campos preenchidos recebe status "Aguardando Envio"                  |
| RN-009.11 | Contratos "Rascunho" não podem ser enviados para Docusign                                        |
| RN-009.12 | O botão "Preview" gera PDF mesmo com campos incompletos                                          |
| RN-009.13 | O campo "Informações Adicionais" é texto livre inserido ao final do corpo do contrato            |
| RN-009.14 | As Condições Comerciais vinculadas devem estar cadastradas no módulo RF-010                      |
| RN-009.15 | Múltiplas Condições Comerciais e Informações Financeiras podem ser adicionadas a um contrato     |

Critérios de Aceitação

**Abertura e Carregamento**

| ID        | Critério                                              | Resultado Esperado                                    |
|-----------|-------------------------------------------------------|-------------------------------------------------------|
| CA-009.01 | Clicar em "Adicionar Contrato" na Gestão de Contratos | Tela abre em modo Novo (campos vazios)                |
| CA-009.02 | Selecionar 1 contrato "Rascunho" e clicar em "Editar" | Tela abre em modo Edição com dados carregados         |
| CA-009.03 | Clicar na linha de um contrato "Ativo"                | Tela abre em modo Visualização (campos desabilitados) |

**Seleção de Tipo de Contrato**

| ID        | Critério                              | Resultado Esperado                                              |
|-----------|---------------------------------------|-----------------------------------------------------------------|
| CA-009.04 | Selecionar usuário Parceiro Comercial | Template de Contrato de Atração é carregado                     |
| CA-009.05 | Selecionar usuário Agência            | Template de Contrato de Agência é carregado                     |
| CA-009.06 | Selecionar Parceiro Comercial         | Campos Razão Social, CNPJ, Endereço preenchidos automaticamente |

**Preenchimento de Campos**

| ID        | Critério                                | Resultado Esperado                                     |
|-----------|-----------------------------------------|--------------------------------------------------------|
| CA-009.07 | Preencher campo no painel direito       | Valor refletido automaticamente no template à esquerda |
| CA-009.08 | Preencher todos os campos obrigatórios  | Barra de progresso atinge 100%                         |
| CA-009.09 | Editar campo preenchido automaticamente | Campo aceita edição                                    |

**Condições e Informações Financeiras**

| ID        | Critério                                    | Resultado Esperado                             |
|-----------|---------------------------------------------|------------------------------------------------|
| CA-009.10 | Clicar em "Criar condição"                  | Novo select de Condição Comercial é adicionado |
| CA-009.11 | Clicar em "Adicionar informação financeira" | Novo bloco de campos financeiros é adicionado  |
| CA-009.12 | Selecionar Condição Comercial               | Condição vinculada ao contrato                 |

**Preview**

| ID        | Critério                                   | Resultado Esperado                                 |
|-----------|--------------------------------------------|----------------------------------------------------|
| CA-009.13 | Clicar em "Preview" com campos incompletos | PDF é baixado com campos preenchidos até o momento |
| CA-009.14 | Clicar em "Preview" com todos os campos    | PDF completo é baixado                             |

**Salvamento**

| ID        | Critério                                           | Resultado Esperado                           |
|-----------|----------------------------------------------------|----------------------------------------------|
| CA-009.15 | Clicar em "Salvar" com campos incompletos          | Modal de confirmação é exibido               |
| CA-009.16 | Confirmar "Salvar como Rascunho"                   | Contrato salvo com status "Rascunho"         |
| CA-009.17 | Clicar em "Continuar Editando" no modal            | Modal fecha e usuário continua editando      |
| CA-009.18 | Clicar em "Salvar" com todos os campos preenchidos | Contrato salvo com status "Aguardando Envio" |
| CA-009.19 | Salvar novo contrato                               | ID é gerado automaticamente                  |

**Modo Visualização**

| ID        | Critério                                      | Resultado Esperado                  |
|-----------|-----------------------------------------------|-------------------------------------|
| CA-009.20 | Abrir contrato "Ativo"                        | Todos os campos estão desabilitados |
| CA-009.21 | Verificar botão "Salvar" em modo Visualização | Botão não é exibido                 |
| CA-009.22 | Clicar em "Preview" em modo Visualização      | PDF do contrato é baixado           |

**Protótipo/Wireframe**

Figura  - WF-008 - Gestão de contratos/adicionar contrato.png

Pendências

| Item                                | Descrição                           |
|-------------------------------------|-------------------------------------|
| emplate Contrato Parceiro Comercial | Cliente deve fornecer modelo        |
| Template Contrato Agência           | Cliente deve fornecer modelo        |
| Campos específicos do template      | Serão documentados após recebimento |

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

**ID:** RF-012

Módulo: Gestão de Atrações

Perfis com Acesso: Administrador

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir que o Administrador visualize, gerencie e acompanhe as atrações cadastradas no sistema. A tela apresenta uma lista de atrações com opções de busca, filtro e ações em massa (editar, excluir, inativar, ativar).

**Requisitos Detalhados**

**Estrutura da Tela**

| ID        | Requisito                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------|
| RF-012.01 | O sistema deve exibir o título "Gestão de Atrações" com subtítulo "Gerencie as atrações do sistema" |
| RF-012.02 | O sistema deve exibir campo de pesquisa por texto (busca por ID, nome ou parceiro comercial)        |
| RF-012.03 | O sistema deve exibir botão "Filtro" ao lado do campo de busca                                      |
| RF-012.04 | O sistema deve exibir botão "Adicionar Atração" que abre o modal de cadastro (RF-013)               |

**Sistema de Abas**

| ID        | Requisito                                                                       |
|-----------|---------------------------------------------------------------------------------|
| RF-012.05 | O sistema deve exibir abas para filtrar atrações: "Ativos", "Inativos", "Todos" |
| RF-012.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela                |
| RF-012.07 | A aba "Ativos" exibe atrações com status: Ativo, Pendente de Contrato, Rascunho |
| RF-012.08 | A aba "Inativos" exibe atrações com status: Inativo, Expirado                   |
| RF-012.09 | A aba "Todos" exibe todas as atrações independente do status                    |

**Tabela de Atrações**

| ID        | Requisito                                                                                                                                  |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| RF-012.10 | O sistema deve exibir tabela com as colunas: Checkbox, ID da Atração, Nome (com foto), Parceiro Comercial (badge), Status, Data de criação |
| RF-012.11 | A coluna Nome deve exibir a foto de capa da atração (thumbnail) + nome da atração                                                          |
| RF-012.12 | A coluna Parceiro Comercial deve exibir o nome do parceiro em formato badge                                                                |
| RF-012.13 | A coluna Status deve exibir badge colorido conforme o status da atração                                                                    |
| RF-012.14 | Cada coluna deve possuir ícone de ordenação (ASC/DESC)                                                                                     |
| RF-012.15 | A ordenação padrão deve ser por ID da Atração DESC (mais recentes primeiro)                                                                |

**Status das Atrações**

| Status               | Cor do Badge   | Descrição                                           |
|----------------------|----------------|-----------------------------------------------------|
| Rascunho             | 🔘 Cinza        | Atração em preenchimento, não finalizada            |
| Pendente de Contrato | 🟡 Amarelo      | Atração cadastrada aguardando contrato ser assinado |
| Ativo                | 🟢 Verde        | Atração publicada e visível no portal               |
| Inativo              | 🔴 Vermelho     | Atração desativada manualmente                      |
| Expirado             | 🟠 Laranja      | Contrato da atração expirou                         |

**Busca e Filtros**

| ID        | Requisito                                                                            |
|-----------|--------------------------------------------------------------------------------------|
| RF-012.16 | O campo de busca deve pesquisar por: ID, Nome da atração, Nome do Parceiro Comercial |
| RF-012.17 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa            |
| RF-012.18 | O botão "Filtro" deve abrir painel com os filtros disponíveis                        |

**Filtros Disponíveis:**

| Filtro             | Tipo             | Descrição                                  |
|--------------------|------------------|--------------------------------------------|
| Parceiro Comercial | Select com busca | Filtrar por parceiro específico            |
| Status             | Multi-select     | Filtrar por um ou mais status              |
| Data de criação    | Range de datas   | Filtrar por período de criação             |
| Com contrato ativo | Checkbox         | Filtrar apenas atrações com contrato ativo |

**Seleção e Ações em Massa**

| ID        | Requisito                                                                                                               |
|-----------|-------------------------------------------------------------------------------------------------------------------------|
| RF-012.19 | O sistema deve permitir seleção múltipla via checkbox na primeira coluna                                                |
| RF-012.20 | Ao selecionar uma ou mais atrações, o sistema deve exibir barra de ações com: contador "Selecionados X", botões de ação |
| RF-012.21 | O checkbox do cabeçalho seleciona/deseleciona todas as atrações da página atual                                         |

**Ações Disponíveis:**

| Ação                  | Quando Aparece                  | Comportamento                                        |
|-----------------------|---------------------------------|------------------------------------------------------|
| Editar                | Apenas 1 selecionado            | Abre modal de edição (RF-013) com campos preenchidos |
| Excluir               | 1 ou mais selecionados          | Exibe confirmação e executa soft delete              |
| Inativar selecionados | Aba "Ativos", 1+ selecionados   | Muda status para "Inativo"                           |
| Ativar selecionados   | Aba "Inativos", 1+ selecionados | Muda status para "Ativo" (se tiver contrato ativo)   |

**Ação de Clique na Linha**

| ID        | Requisito                                                                                                                           |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| RF-012.22 | Ao clicar em uma linha da tabela (não no checkbox), o sistema deve abrir o modal de edição da atração (RF-013) em modo visualização |
| RF-012.23 | No modal de visualização, todos os campos devem estar desabilitados para edição                                                     |
| RF-012.24 | O modal de visualização deve exibir botão "Habilitar Edição" para permitir alterações                                               |

**Paginação**

| ID        | Requisito                                                                                                  |
|-----------|------------------------------------------------------------------------------------------------------------|
| RF-012.25 | O sistema deve exibir por padrão 10 registros por página                                                   |
| RF-012.26 | O sistema deve permitir alterar para: 10, 20, 50, 100 registros por página                                 |
| RF-012.27 | O sistema deve exibir navegação: Primeira página, Anterior, Indicador (X a Y de Z), Próxima, Última página |

**Regras de Negócio**

| #         | Regra                                                                                                                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-012.01 | Soft Delete: Ao excluir uma atração, o sistema deve marcar como "Excluído" no banco de dados (não remove fisicamente)                                                                                                                                   |
| RN-012.02 | Impacto no Contrato: Ao excluir ou inativar uma atração que possui contrato vinculado, o sistema deve exibir alerta: "Esta atração possui contrato vinculado. Ao excluir/inativar, o contrato será alterado para status 'Cancelado'. Deseja continuar?" |
| RN-012.03 | Recuperação: Atrações excluídas NÃO podem ser recuperadas pelo Administrador (apenas equipe de TI via banco de dados)                                                                                                                                   |
| RN-012.04 | Reativação: Atrações inativadas podem ser reativadas pela aba "Inativos", desde que possuam contrato ativo                                                                                                                                              |
| RN-012.05 | Reativação sem contrato: Ao tentar ativar uma atração sem contrato ativo, exibir mensagem: "Esta atração não possui contrato ativo. Crie um contrato antes de ativá-la."                                                                                |
| RN-012.06 | Visibilidade no Portal: Apenas atrações com status "Ativo" são visíveis para turistas no portal público                                                                                                                                                 |

Critérios de Aceitação

| #         | Critério                                                                                                                                                        |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-012.01 | Dado que o Administrador acessa a tela de Gestão de Atrações, quando a página carrega, então deve exibir a lista de atrações ativas ordenadas por ID DESC       |
| CA-012.02 | Dado que o Administrador seleciona uma atração e clica em "Editar", quando o modal abre, então deve exibir todos os dados da atração nos campos correspondentes |
| CA-012.03 | Dado que o Administrador exclui uma atração com contrato vinculado, quando confirma a exclusão, então o contrato deve ter seu status alterado para "Cancelado"  |
| CA-012.04 | Dado que o Administrador clica em uma linha da tabela, quando o modal abre, então os campos devem estar desabilitados (modo visualização)                       |
| CA-012.05 | Dado que o Administrador pesquisa por "Ópera", quando a busca é executada, então deve retornar todas as atrações que contenham "Ópera" no nome                  |

**Protótipo/Wireframe**

Figura  - WF-012 - Gestão de Atrações

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

**ID:** RF-014

**Módulo:** Detalhes da Atração &gt; Categorias

**Perfis com Acesso:** Administrador, Parceiro Comercial, Editor

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve permitir a gestão centralizada das categorias de ingresso (tipos de público) vinculadas a uma atração específica. Categorias definem os tipos de ingresso disponíveis (Ex: Estudante, Adulto, Idoso, Doador de Sangue, Morador de Curitiba), enquanto valores e quantidades são configurados separadamente na Gestão de Ingressos/Lotes.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                   |
|-----------|---------------------------------------------------------------------------------------------|
| RF-014.01 | O sistema deve exibir título "Categorias" com subtítulo "Gerencie as categorias da atração" |
| RF-014.02 | O sistema deve exibir campo de pesquisa para buscar por ID ou Nome da categoria             |
| RF-014.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                 |
| RF-014.04 | O sistema deve exibir botão "Adicionar Categoria" que abre o modal de criação               |

Sistema de Abas

| ID        | Requisito                                                                                    |
|-----------|----------------------------------------------------------------------------------------------|
| RF-014.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos"                      |
| RF-014.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela                             |
| RF-014.07 | Ao alternar entre abas, a tabela deve atualizar exibindo apenas os registros correspondentes |

Tabela de Categorias

| ID        | Requisito                                                                                  |
|-----------|--------------------------------------------------------------------------------------------|
| RF-014.08 | O sistema deve exibir tabela com colunas: Checkbox (seleção), ID, Categoria (nome), Status |
| RF-014.09 | A coluna Status deve exibir badges: "Ativo" (verde) ou "Inativo" (cinza)                   |
| RF-014.10 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                        |
| RF-014.11 | A tabela deve ser ordenada por ID DESC por padrão                                          |

Busca e Filtros

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-014.12 | O campo de pesquisa deve buscar por ID ou Nome da categoria                                     |
| RF-014.13 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                       |
| RF-014.14 | O botão Filtro deve abrir painel com filtros: Status (Ativo/Inativo), Data de Criação (período) |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-014.15 | O sistema deve permitir seleção múltipla via checkbox                                                       |
| RF-014.16 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Editar, Excluir, Inativar (toggle) |
| RF-014.17 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                            |

Ações Disponíveis

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-014.18 | **Editar**  : Disponível apenas quando 1 item selecionado. Abre modal de edição                             |
| RF-014.19 | **Excluir**  : Exibe confirmação "Deseja excluir X categoria(s) selecionada(s)?". Permite exclusão em massa |
| RF-014.20 | **Inativar**  : Altera status para "Inativo". Permite inativação em massa                                   |
| RF-014.21 | **Ativar**  (aba Inativos): Altera status para "Ativo". Permite ativação em massa                           |
| RF-014.22 | O toggle Inativar/Ativar na barra de ações deve alternar conforme a aba ativa                               |

Ação de Clique na Linha

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-014.23 | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-014.24 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-014.25 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-014.26 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Categoria

| ID        | Requisito                                                                                                                                  |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| RF-014.27 | O modal deve exibir título dinâmico: "Adicionar Categoria" (novo), "Editar Categoria" (edição) ou "Visualizar Categoria" (somente leitura) |
| RF-014.28 | Campos do modal: ID (somente leitura, gerado automaticamente), Nome da Categoria (obrigatório, máx 100 caracteres), Status (Ativo/Inativo) |
| RF-014.29 | No modo Adicionar: campo ID não aparece, Status padrão "Ativo"                                                                             |
| RF-014.30 | No modo Editar: todos os campos editáveis exceto ID                                                                                        |
| RF-014.31 | No modo Visualizar: todos os campos somente leitura                                                                                        |
| RF-014.32 | O modal deve exibir campos de auditoria (somente leitura): Data de Criação, Última Atualização                                             |
| RF-014.33 | Botões: Salvar e Cancelar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                                                      |
| RF-014.34 | Ao salvar nova categoria, o sistema deve gerar ID único automaticamente e vincular à atração atual                                         |
| RF-014.35 | Ao salvar, o modal deve fechar e a tabela deve ser atualizada                                                                              |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                     |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-014.01 | Categorias são sempre vinculadas a uma atração específica (não são globais)                                                                                                               |
| RN-014.02 | O sistema deve impedir a exclusão de categorias que já foram utilizadas em ingressos vendidos. Mensagem: "Esta categoria não pode ser excluída pois possui ingressos vendidos vinculados" |
| RN-014.03 | O sistema deve impedir a inativação de categorias com ingressos com status "Vendido" ou "Validado" pendentes                                                                              |
| RN-014.04 | O nome da categoria deve ser único dentro da mesma atração. Mensagem de erro: "Já existe uma categoria com este nome nesta atração"                                                       |
| RN-014.05 | Categorias criadas aqui ficam disponíveis para seleção na Gestão de Ingressos/Lotes                                                                                                       |
| RN-014.06 | Categorias inativas não aparecem como opção na criação de novos ingressos/lotes                                                                                                           |
| RN-014.07 | O ID da categoria é gerado automaticamente pelo sistema de forma incremental                                                                                                              |
| RN-014.08 | Exclusão é soft delete (marcação no banco de dados). Categorias excluídas não aparecem em nenhuma aba                                                                                     |
| RN-014.09 | Categorias excluídas só podem ser recuperadas pela equipe de TI via banco de dados                                                                                                        |
| RN-014.10 | Esta funcionalidade é a mesma acessada pelo botão "Adicionar categoria" no cadastro de atrações (RF-013)                                                                                  |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                           |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-014.01 | Dado que o usuário acessa Detalhes da Atração > Categorias, então deve visualizar a lista de categorias da atração selecionada na aba "Ativos"                     |
| CA-014.02 | Dado que o usuário clica em "Adicionar Categoria", quando preenche o nome e salva, então a categoria deve aparecer na lista com status "Ativo"                     |
| CA-014.03 | Dado que existe uma categoria vinculada a ingressos vendidos, quando o usuário tenta excluí-la, então o sistema deve exibir mensagem de erro e impedir a exclusão  |
| CA-014.04 | Dado que o usuário seleciona múltiplas categorias, quando clica em "Inativar", então todas devem ter seu status alterado para "Inativo"                            |
| CA-014.05 | Dado que o usuário está na aba "Inativos", quando seleciona categorias e clica em "Ativar", então elas devem voltar para status "Ativo" e aparecer na aba "Ativos" |
| CA-014.06 | Dado que o usuário clica em uma linha da tabela (fora do checkbox), então deve abrir o modal de visualização com campos somente leitura                            |
| CA-014.07 | Dado que o usuário tenta criar categoria com nome já existente na atração, então o sistema deve exibir erro de duplicidade                                         |
| CA-014.08 | Dado que o usuário altera a paginação para 50 itens, então a tabela deve exibir até 50 registros por página                                                        |

**Protótipo/Wireframe**

Figura  - WF-016 - Detalhes da Atração/Categorias.png

### 3.15 Detalhes da Atrações/Pesquisar Ingresso – Administrador

**ID:** RF-015

**Módulo:** Detalhes da Atração &gt; Pesquisar Ingresso

**Perfis:** Administrador, Parceiro Comercial, Editor, Leitor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a pesquisa, visualização e gestão dos ingressos emitidos para uma atração específica. A tela apresenta uma lista de ingressos com opções de busca, filtro e ações em massa (validar, reenviar, visualizar QR Code, cancelar, inativar). Esta funcionalidade serve como alternativa para validação manual de ingressos quando houver problemas com o leitor de QR Code.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-015.01 | O sistema deve exibir título "Pesquisar Ingresso" com subtítulo "Gerencie os ingressos emitidos" |
| RF-015.02 | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                 |
| RF-015.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                      |
| RF-015.04 | A tela NÃO possui botão de adicionar (ingressos são criados apenas via compra)                   |

Sistema de Abas

| ID        | Requisito                                                               |
|-----------|-------------------------------------------------------------------------|
| RF-015.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
| RF-015.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
| RF-015.07 | A aba "Ativos" deve exibir ingressos com status: Vendido, Validado      |
| RF-015.08 | A aba "Inativos" deve exibir ingressos com status: Cancelado, Inativado |
| RF-015.09 | A aba "Todos" deve exibir todos os ingressos independente do status     |

Tabela de Ingressos

| ID        | Requisito                                                                                                                 |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RF-015.10 | O sistema deve exibir tabela com colunas: Checkbox, ID, Código, Status, Atração, Categoria, Localização, Data Hora Pedido |
| RF-015.11 | A coluna "Status" deve exibir badges coloridos conforme o status do ingresso                                              |
| RF-015.12 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                                                       |
| RF-015.13 | A tabela deve ser ordenada por Data Hora Pedido DESC por padrão                                                           |

Status dos Ingressos

| ID        | Requisito                                                                          |
|-----------|------------------------------------------------------------------------------------|
| RF-015.14 | Vendido (badge verde): Ingresso emitido, pagamento confirmado, ainda não utilizado |
| RF-015.15 | Validado (badge azul): Ingresso já utilizado para entrada na atração               |
| RF-015.16 | Cancelado (badge cinza): Ingresso estornado e cancelado                            |
| RF-015.17 | Inativado (badge vermelho): Ingresso bloqueado manualmente pelo administrador      |

Busca e Filtros

| ID        | Requisito                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------|
| RF-015.18 | O campo de pesquisa deve buscar por: ID, Código, Atração, Categoria, Localização                       |
| RF-015.19 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                              |
| RF-015.20 | O botão Filtro deve abrir painel com filtros: Status, Categoria, Data do Pedido (período), Localização |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                                                                         |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-015.21 | O sistema deve permitir seleção múltipla via checkbox                                                                                                             |
| RF-015.22 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Validar ingresso, Reenviar ingresso, Visualizar QR Code, Cancelar, Inativar selecionados |
| RF-015.23 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                                                                                  |

Ações Disponíveis

| ID        | Requisito                                                                                                                                |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------|
| RF-015.24 | Validar ingresso: Altera status de "Vendido" para "Validado". Permite validação em massa. Funciona sem necessidade de escanear QR Code   |
| RF-015.25 | Reenviar ingresso: Reenvia o ingresso por e-mail E SMS para o cliente. Permite reenvio em massa                                          |
| RF-015.26 | Visualizar QR Code: Abre modal exibindo a imagem do QR Code. Permite download e impressão. Disponível apenas para 1 ingresso selecionado |
| RF-015.27 | Cancelar: Comportamento varia conforme status atual do ingresso (ver Regras de Negócio)                                                  |
| RF-015.28 | Inativar selecionados: Altera status para "Inativado". Permite inativação em massa. Bloqueia o ingresso na entrada da atração            |

Ação de Clique na Linha

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-015.29 | Ao clicar em uma linha (fora do checkbox), abrir modal "Detalhes do Ingresso" (RF-016) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-015.30 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-015.31 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-015.32 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Regras de Negócio

| ID        | Regra                                                                                                                                |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------|
| RN-015.01 | Ingressos são criados automaticamente quando o pagamento do pedido é confirmado                                                      |
| RN-015.02 | Um pedido pode gerar múltiplos ingressos (ex: cliente compra 3 ingressos no mesmo pedido)                                            |
| RN-015.03 | Cancelar ingresso "Validado": Sistema pede confirmação. Se confirmado, status volta para "Vendido" (permite nova entrada)            |
| RN-015.04 | Cancelar ingresso "Vendido": Sistema exibe mensagem de confirmação com aviso de estorno. Se confirmado, status muda para "Cancelado" |
| RN-015.05 | Ingressos com status "Inativado" são bloqueados ao serem escaneados na entrada. Sistema exibe notificação ao validador               |
| RN-015.06 | A ação "Validar ingresso" só está disponível para ingressos com status "Vendido"                                                     |
| RN-015.07 | A ação "Cancelar" só está disponível para ingressos com status "Vendido" ou "Validado"                                               |
| RN-015.08 | A ação "Inativar" só está disponível para ingressos com status "Vendido"                                                             |
| RN-015.09 | Ingressos com status "Cancelado" ou "Inativado" não podem ter ações executadas (apenas visualização)                                 |
| RN-015.10 | O perfil Leitor tem acesso limitado: pode apenas pesquisar e visualizar, não pode executar ações                                     |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                          |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-015.01 | Dado que o usuário acessa Detalhes da Atração > Pesquisar Ingresso, então deve visualizar a lista de ingressos na aba "Ativos"                                                    |
| CA-015.02 | Dado que o usuário seleciona um ingresso com status "Vendido" e clica em "Validar", então o status deve mudar para "Validado"                                                     |
| CA-015.03 | Dado que o usuário seleciona um ingresso com status "Validado" e clica em "Cancelar", quando confirma, então o status deve voltar para "Vendido"                                  |
| CA-015.04 | Dado que o usuário seleciona um ingresso com status "Vendido" e clica em "Cancelar", quando confirma, então o status deve mudar para "Cancelado" e o pagamento deve ser estornado |
| CA-015.05 | Dado que o usuário clica em "Reenviar ingresso", então o ingresso deve ser enviado por e-mail E SMS ao cliente                                                                    |
| CA-015.06 | Dado que um ingresso está com status "Inativado" e é escaneado na entrada, então o sistema deve bloquear e exibir notificação ao validador                                        |
| CA-015.07 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de detalhes do ingresso                                                                                 |

**Protótipo/Wireframe**

Figura  - Detalhes da Atrações/Pesquisar Ingresso – Administrador

### 3.16 Detalhes da Atrações/Pesquisar Ingresso/Detalhes – Administrador

**ID:** RF-016

**Módulo** : Detalhes da Atração &gt; Pesquisar Ingresso &gt; Detalhes

**Perfis** : Administrador, Parceiro Comercial, Editor, Leitor

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve exibir um modal com informações detalhadas do ingresso selecionado, incluindo dados do pedido, dados do cliente e dados específicos do ingresso. O modal é somente visualização, sem opções de edição ou ações.

Requisitos Detalhados

Estrutura do Modal

| ID        | Requisito                                                                   |
|-----------|-----------------------------------------------------------------------------|
| RF-016.01 | O modal deve exibir título dinâmico: "Detalhes do ingresso código [CÓDIGO]" |
| RF-016.02 | O modal deve exibir botão de fechar (X) no canto superior direito           |
| RF-016.03 | O modal é somente visualização (não permite edição de nenhum campo)         |
| RF-016.04 | O modal NÃO possui botões de ação (Validar, Cancelar, etc.)                 |

Seção: Pedido

| ID        | Requisito                                                                                        |
|-----------|--------------------------------------------------------------------------------------------------|
| RF-016.05 | O sistema deve exibir seção "Pedido" com os dados do pedido original                             |
| RF-016.06 | Campos da seção Pedido: Código, Status, Forma de Pagamento, Vendedor, Data Hora Pedido, Obs      |
| RF-016.07 | O campo "Status do Pedido" deve exibir: Reservado, Finalizado, Cancelado ou Expirado             |
| RF-016.08 | O campo "Vendedor" deve exibir quem intermediou a venda (Agente/Agência ou indicar venda direta) |
| RF-016.09 | O campo "Obs" exibe a mensagem customizada definida na criação do ingresso (RF-017)              |

Status do Pedido

| ID        | Requisito                                                                 |
|-----------|---------------------------------------------------------------------------|
| RF-016.10 | Reservado: Pedido criado, aguardando pagamento                            |
| RF-016.11 | Finalizado: Pedido pago e ingressos emitidos                              |
| RF-016.12 | Cancelado: Pedido cancelado pelo operadora de pagamentos ou administrador |
| RF-016.13 | Expirado: Pedido não pago dentro do prazo de expiração                    |

Seção: Dados do Cliente

| ID        | Requisito                                                                   |
|-----------|-----------------------------------------------------------------------------|
| RF-016.14 | O sistema deve exibir seção "Dados do cliente" com informações do comprador |
| RF-016.15 | Campos da seção: Nome, Email, CPF/CNPJ, Telefone, Celular                   |
| RF-016.16 | Os dados do cliente são os informados no momento da compra                  |

Seção: Dados do Ingresso

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-016.17 | O sistema deve exibir seção "Dados do Ingresso" com informações específicas do ingresso                  |
| RF-016.18 | Campos da seção (linha 1): Código, Atração, Categoria, Localização, PDV                                  |
| RF-016.19 | Campos da seção (linha 2): Status, Data Criação, Data Impressão, Valor, Taxa Administrativa, Valor Total |
| RF-016.20 | O campo "Categoria" exibe o tipo de ingresso (ex: Morador de Curitiba Adulto, Estudante, Idoso)          |
| RF-016.21 | O campo "Localização" exibe o nome personalizado do local de acesso do ingresso                          |
| RF-016.22 | O campo "PDV" (Ponto de Venda) exibe: "Site" ou "App"                                                    |
| RF-016.23 | O campo "Valor Total" = Valor + Taxa Administrativa                                                      |

Regras de Negócio

| ID        | Regra                                                                                                                  |
|-----------|------------------------------------------------------------------------------------------------------------------------|
| RN-016.01 | Um pedido pode ter múltiplos ingressos. O modal exibe os dados de apenas um ingresso por vez                           |
| RN-016.02 | O campo "Vendedor" exibe o nome do Agente/Agência que intermediou a venda, ou o nome da plataforma para vendas diretas |
| RN-016.03 | A "Data Impressão" é preenchida quando o cliente visualiza/baixa o ingresso pela primeira vez                          |
| RN-016.04 | Se o ingresso nunca foi impresso/visualizado, o campo "Data Impressão" fica vazio                                      |
| RN-016.05 | O campo "Obs" é somente leitura e vem preenchido automaticamente conforme configuração da categoria                    |

Critérios de Aceitação

| ID        | Critério                                                                                                                                   |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------|
| CA-016.01 | Dado que o usuário clica em uma linha na tela de Pesquisar Ingresso, então deve abrir o modal com os detalhes do ingresso selecionado      |
| CA-016.02 | Dado que o modal está aberto, então todos os campos devem estar em modo somente leitura                                                    |
| CA-016.03 | Dado que o usuário clica no botão X, então o modal deve fechar e retornar à lista de ingressos                                             |
| CA-016.04 | Dado que o ingresso pertence a um pedido com múltiplos ingressos, então o modal deve exibir apenas os dados do ingresso específico clicado |
| CA-016.05 | Dado que a venda foi intermediada por um agente, então o campo "Vendedor" deve exibir o nome do agente                                     |

**Protótipo/Wireframe**

Figura  - WF-018 - Detalhes da Atração/Pesquisar Ingresso/Detalhe do Ingresso

### 3.17 Detalhes da Atrações/Gestão de Ingressos – Administrador.

**ID:** RF-017

**Módulo** : Detalhes da Atração &gt; Gestão de Ingressos

**Perfis** : Administrador, Parceiro Comercial, Editor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a gestão dos ingressos (lotes) vinculados a uma atração específica. Cada ingresso configura um lote de venda com categoria, valor, quantidade disponível e outras características. Um mesmo tipo de categoria pode ter múltiplos lotes com valores e quantidades diferentes.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------|
| RF-017.01 | O sistema deve exibir título "Gestão de Ingresso" com subtítulo "Gerencie os ingressos da atração" |
| RF-017.02 | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                   |
| RF-017.03 | O sistema deve exibir botão "Filtro" para filtros avançados                                        |
| RF-017.04 | O sistema deve exibir botão "Adicionar Ingresso" que abre o modal de criação                       |

Sistema de Abas

| ID        | Requisito                                                               |
|-----------|-------------------------------------------------------------------------|
| RF-017.05 | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
| RF-017.06 | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
| RF-017.07 | A aba "Ativos" deve exibir ingressos com status "Ativo"                 |
| RF-017.08 | A aba "Inativos" deve exibir ingressos com status "Inativo"             |

Tabela de Ingressos

| ID        | Requisito                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| RF-017.09 | O sistema deve exibir tabela com colunas: Checkbox, ID, Categorias, Status, Valor, Quantidade, Lote, Msg Customizada, Expiração do Pedido (h) |
| RF-017.10 | A coluna "Status" deve exibir badges: "Ativo" (azul) ou "Inativo" (cinza)                                                                     |
| RF-017.11 | Cada coluna deve permitir ordenação ASC/DESC ao clicar no cabeçalho                                                                           |
| RF-017.12 | A tabela deve ser ordenada por ID DESC por padrão                                                                                             |

Busca e Filtros

| ID        | Requisito                                                                 |
|-----------|---------------------------------------------------------------------------|
| RF-017.13 | O campo de pesquisa deve buscar por: ID, Categoria, Lote, Valor           |
| RF-017.14 | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa |
| RF-017.15 | O botão Filtro deve abrir painel com filtros: Status, Categoria, Lote     |

Seleção e Ações em Massa

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-017.16 | O sistema deve permitir seleção múltipla via checkbox                                                       |
| RF-017.17 | Ao selecionar um ou mais itens, exibir barra de ações: "Selecionados X", Editar, Excluir, Inativar (toggle) |
| RF-017.18 | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                            |

Ações Disponíveis

| ID        | Requisito                                                                    |
|-----------|------------------------------------------------------------------------------|
| RF-017.19 | Editar: Disponível apenas quando 1 item selecionado. Abre modal de edição    |
| RF-017.20 | Excluir: Exibe confirmação antes de executar. Permite exclusão em massa      |
| RF-017.21 | Inativar: Altera status para "Inativo". Permite inativação em massa          |
| RF-017.22 | Ativar (aba Inativos): Altera status para "Ativo". Permite ativação em massa |

Ação de Clique na Linha

| ID        | Requisito                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------|
| RF-017.23 | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-017.24 | O sistema deve exibir 10 registros por padrão                                                            |
| RF-017.25 | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
| RF-017.26 | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Ingresso

| ID        | Requisito                                                                                                                               |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------|
| RF-017.27 | O modal deve exibir título dinâmico: "Novo Ingresso" (novo) ou "Editar Ingresso" (edição) ou "Visualizar Ingresso" (somente leitura)    |
| RF-017.28 | O modal deve exibir subtítulo: "Preencha os campos obrigatórios para adicionar um ingresso"                                             |
| RF-017.29 | O modal deve exibir botões: Descartar e Salvar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                              |
| RF-017.30 | Campo Categoria (obrigatório): Dropdown que lista categorias cadastradas na atração (RF-014). Permite busca por nome                    |
| RF-017.31 | Campo Valor (obrigatório): Campo numérico monetário com máscara R$ 0,00                                                                 |
| RF-017.32 | Campo Lote (obrigatório): Campo texto para número do lote (ex: 001, 002)                                                                |
| RF-017.33 | Campo Quantidade (obrigatório): Campo numérico para quantidade máxima de ingressos disponíveis para venda                               |
| RF-017.34 | Campo Expiração do pedido (h) (obrigatório): Campo numérico para tempo em horas que o cliente tem para pagar após adicionar ao carrinho |
| RF-017.35 | Campo Mensagem Customizada (opcional): Campo texto para mensagem que aparecerá no ingresso do cliente                                   |
| RF-017.36 | Campo Ativo (obrigatório): Toggle switch para ativar/desativar o ingresso. Padrão: Ativo                                                |

Regras de Negócio

| ID        | Regra                                                                                                                    |
|-----------|--------------------------------------------------------------------------------------------------------------------------|
| RN-017.01 | Cada ingresso possui apenas uma categoria vinculada                                                                      |
| RN-017.02 | Um mesmo tipo de categoria pode ter múltiplos lotes com valores e quantidades diferentes                                 |
| RN-017.03 | O número do lote deve ser único dentro da mesma atração                                                                  |
| RN-017.04 | Ingressos são sempre vinculados a uma atração específica (não são globais)                                               |
| RN-017.05 | O ID do ingresso é gerado automaticamente pelo sistema de forma incremental                                              |
| RN-017.06 | A mensagem customizada aparece no ingresso físico/digital do cliente após a compra                                       |
| RN-017.07 | A quantidade define o máximo de ingressos que podem ser vendidos para aquele lote                                        |
| RN-017.08 | Ao atingir a quantidade máxima vendida, o lote deve ser automaticamente inativado ou o sistema deve impedir novas vendas |
| RN-017.09 | Exclusão deve ser soft delete (marcação no banco de dados, não remoção física)                                           |
| RN-017.10 | Ingressos excluídos não aparecem em nenhuma aba e só podem ser recuperados pela equipe de TI                             |
| RN-017.11 | Ingressos inativos não aparecem como opção de compra para clientes                                                       |
| RN-017.12 | O sistema deve impedir a exclusão de ingressos que possuem vendas vinculadas                                             |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                     |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-017.01 | Dado que o usuário acessa Detalhes da Atração > Gestão de Ingressos, então deve visualizar a lista de ingressos na aba "Ativos"                                              |
| CA-017.02 | Dado que o usuário clica em "Adicionar Ingresso", quando preenche os campos obrigatórios e salva, então o ingresso deve aparecer na lista                                    |
| CA-017.03 | Dado que existe uma categoria "Estudante" com lote 001 (R$ 10,00), quando o usuário cria outro ingresso "Estudante" lote 002 (R$ 15,00), então ambos devem aparecer na lista |
| CA-017.04 | Dado que o usuário tenta criar ingresso com número de lote já existente na atração, então o sistema deve exibir erro de duplicidade                                          |
| CA-017.05 | Dado que o usuário seleciona múltiplos ingressos e clica em "Inativar", então todos devem ter seu status alterado para "Inativo"                                             |
| CA-017.06 | Dado que um lote atinge sua quantidade máxima vendida, então o sistema deve impedir novas vendas ou inativar automaticamente                                                 |
| CA-017.07 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de visualização com campos somente leitura                                                         |
| CA-017.08 | Dado que o usuário tenta excluir um ingresso com vendas vinculadas, então o sistema deve exibir erro e impedir a exclusão                                                    |

**Protótipo/Wireframe**

Figura  - WF-019 - Detalhes da Atração/Gestão de ingresso

Figura - WF-020 - Detalhes da Atração/Gestão de Ingresso/Adicionar Ingresso

### 3.18 Detalhes da Atrações/Gestão de Cupons – Administrador

**ID:** RF-018

**Módulo** : Detalhes da Atração &gt; Gestão de Cupons

**Perfis** : Administrador, Parceiro Comercial, Editor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir a gestão de cupons de desconto vinculados a uma atração específica. Os cupons podem ser de dois tipos: Cupom Normal (disponível para todos os turistas) e Cupom Agência (vinculado a uma agência específica para controle de comissões). Cada cupom possui tipo de desconto (porcentagem ou valor fixo), quantidade máxima de usos, validade por período e dias da semana, categorias aplicáveis, e pode ser compartilhado via link único ou QR Code.

Requisitos Detalhados

Estrutura da Tela

| ID   | Requisito                                                                                          |
|------|----------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir título "Gestão de Cupons" com subtítulo "Gerencie os cupons da atração"      |
|      | O sistema deve exibir campo de pesquisa para buscar por qualquer campo da tabela                   |
|      | O sistema deve exibir botão "Filtro" para filtros avançados                                        |
|      | O sistema deve exibir botão "Adicionar Cupom" que abre o modal de criação de cupom normal          |
|      | O sistema deve exibir botão "Adicionar Cupom Agencia" que abre o modal de criação de cupom agência |

Sistema de Abas

| ID   | Requisito                                                               |
|------|-------------------------------------------------------------------------|
|      | O sistema deve exibir abas para filtrar: "Ativos", "Inativos" e "Todos" |
|      | A aba "Ativos" deve ser selecionada por padrão ao acessar a tela        |
|      | A aba "Ativos" deve exibir cupons com status "Ativo"                    |
|      | A aba "Inativos" deve exibir cupons com status "Inativo" ou "Expirado"  |

Tabela de Cupons

| ID   | Requisito                                                                                                                                                                                                  |
|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir tabela com colunas: Checkbox, ID, Nome, Usuário Relacionado, Status, Porcentagem/valor, Valor, Quantidade, Link, Saldo, Mostrar na Atração, Dias da semana, Início, Final, Categoria |
|      | A coluna "Status" deve exibir badges: "Ativo" (azul), "Inativo" (cinza) ou "Expirado" (vermelho)                                                                                                           |
|      | A coluna "Porcentagem/valor" deve exibir "Porcentagem" ou "Valor" conforme o tipo de desconto                                                                                                              |
|      | A coluna "Valor" deve exibir "% 10%" quando tipo for Porcentagem ou "R$ 10,00" quando tipo for Valor                                                                                                       |
|      | A coluna "Link" deve exibir o link caso já tenha sido gerado e um botão para copiar o link.                                                                                                                |
|      | A coluna "Saldo" deve exibir a quantidade restante (Quantidade - Utilizados) e atualizar automaticamente quando o cupom é usado                                                                            |

Busca e Filtros

| ID   | Requisito                                                                                                       |
|------|-----------------------------------------------------------------------------------------------------------------|
|      | O campo de pesquisa deve buscar por: ID, Nome, Categoria                                                        |
|      | A busca deve ser executada ao pressionar Enter ou clicar no ícone de lupa                                       |
|      | O botão Filtro deve abrir painel com filtros: Status, Tipo (Normal/Agência), Categoria, Data Início, Data Final |

Seleção e Ações em Massa

| ID   | Requisito                                                                                                                           |
|------|-------------------------------------------------------------------------------------------------------------------------------------|
|      | O sistema deve permitir seleção múltipla via checkbox                                                                               |
|      | Ao selecionar mais itens, exibir barra de ações: "Selecionados X", Gerar link, Excluir, Inativar (toggle)                           |
|      | Ao selecionar apenas um item, exibir barra de ações: "Selecionados X", Gerar link, Compartilhar, Editar, Excluir, Inativar (toggle) |
|      | O checkbox no cabeçalho deve selecionar/desmarcar todos os itens da página atual                                                    |
|      | A ação "Gerar link" deve estar disponível para múltiplos cupons selecionados                                                        |
|      | A ação "Compartilhar" deve estar disponível para múltiplos cupons selecionados                                                      |

Ações Disponíveis

| ID   | Requisito                                                                                                         |
|------|-------------------------------------------------------------------------------------------------------------------|
|      | Gerar link: Cria link único para o cupom (ex: curitiba360.com/joao10). Abre modal de QR Code com o link e QR Code |
|      | Compartilhar: Gera o link (se não existir) e abre WhatsApp para compartilhar o link do cupom                      |
|      | Editar: Disponível apenas quando 1 item selecionado. Abre modal de edição                                         |
|      | Excluir: Exibe confirmação antes de executar. Permite exclusão em massa                                           |
|      | Inativar: Altera status para "Inativo". Permite inativação em massa                                               |
|      | Ativar (aba Inativos): Altera status para "Ativo". Permite ativação em massa                                      |

Ação de Clique na Linha

| ID   | Requisito                                                                                       |
|------|-------------------------------------------------------------------------------------------------|
|      | Ao clicar em uma linha (fora do checkbox), abrir modal de visualização (campos somente leitura) |

Paginação

| ID   | Requisito                                                                                                |
|------|----------------------------------------------------------------------------------------------------------|
|      | O sistema deve exibir 10 registros por padrão                                                            |
|      | O sistema deve permitir alterar para 20, 50 ou 100 registros por página                                  |
|      | A navegação deve incluir: primeira página, anterior, página atual (ex: "1 a 10 de 200"), próxima, última |

Modal Adicionar/Editar Cupom (Normal)

| ID   | Requisito                                                                                                                                                    |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O modal deve exibir título dinâmico: "Novo Cupom" (novo) ou "Editar Cupom" (edição) ou "Visualizar Cupom" (somente leitura)                                  |
|      | O modal deve exibir subtítulo: "Preencha os campos obrigatórios para adicionar um cupom"                                                                     |
|      | O modal deve exibir botões: Descartar e Salvar (modos Adicionar/Editar) ou apenas Fechar (modo Visualizar)                                                   |
|      | Campo Usuário Relacionado (obrigatório): Campo de seleção única e pesquisável com o nome do usuário que irá receber a comissão                               |
|      | Campo Nome (obrigatório): Campo texto para nome do cupom (ex: JOAO10)                                                                                        |
|      | Campo Porcentagem/Valor (obrigatório): Dropdown com opções "Porcentagem" ou "Valor"                                                                          |
|      | Campo Valor (obrigatório): Campo numérico. Se Porcentagem: exibir "% 10%". Se Valor: exibir "R$ 10,00"                                                       |
|      | Campo Quantidade (obrigatório): Campo numérico para quantidade máxima de ingressos com desconto                                                              |
|      | Campo Mostrar na atração (obrigatório): Radio buttons "Sim" ou "Não". Quando "Sim", cupom aparece na página principal da atração                             |
|      | Campo Início (obrigatório): Date/time picker para início da validade do cupom                                                                                |
|      | Campo Fim (obrigatório): Date/time picker para fim da validade do cupom                                                                                      |
|      | Campo Categorias (obrigatório): Multiseleção com checkboxes das categorias cadastradas na atração (RF-014). Cupom válido para qualquer categoria selecionada |
|      | Campo Ativo (obrigatório): Toggle switch para ativar/desativar o cupom. Padrão: Ativo                                                                        |

Modal Adicionar/Editar Cupom Agência

| ID   | Requisito                                                                                                                                                                                     |
|------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      | O modal deve conter todos os campos do Cupom Normal (RF-018.33 a RF-018.45) mais o campo Agência (obrigatório): Dropdown que lista todas as agências cadastradas, permite digitar para buscar |

Modal QR Code

| ID   | Requisito                                                                                   |
|------|---------------------------------------------------------------------------------------------|
|      | O modal deve exibir título "QR Code"                                                        |
|      | O modal deve exibir instrução: "Escaneie o QR Code ou copie o link"                         |
|      | O modal deve exibir QR Code gerado para o link do cupom                                     |
|      | O modal deve exibir campo com o link do cupom (ex: curitiba360.com/joao10) e botão "Copiar" |

Regras de Negócio

| ID        | Regra                                                                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-018.01 | Cupons são sempre vinculados a uma atração específica (não são globais)                                                                          |
| RN-018.02 | O ID do cupom é gerado automaticamente pelo sistema de forma incremental                                                                         |
| RN-018.03 | O nome do cupom deve ser único dentro da mesma atração                                                                                           |
| RN-018.04 | Cupom Normal é disponível para todos os turistas e visitantes da plataforma                                                                      |
| RN-018.05 | Cupom Agência é vinculado a uma agência específica para controle de comissões. A agência divulga o cupom, mas pode ser usado por qualquer pessoa |
| RN-018.06 | O saldo do cupom (Quantidade - Utilizados) deve ser atualizado automaticamente quando o cupom é usado em uma compra                              |
| RN-018.07 | O link do cupom é gerado automaticamente quando o usuário clica em "Gerar link" ou "Compartilhar"                                                |
| RN-018.08 | O link do cupom é único e pode ser compartilhado e usado por qualquer pessoa                                                                     |
| RN-018.09 | O link permite múltiplos usos até atingir a quantidade máxima                                                                                    |
| RN-018.10 | Quando "Mostrar na Atração" está como "Sim", o cupom aparece no checkout da atração                                                              |
| RN-018.11 | Quando múltiplas categorias são selecionadas, o cupom é válido para qualquer uma delas                                                           |
| RN-018.12 | O cupom pode ser usado apenas nos dias da semana selecionados                                                                                    |
| RN-018.13 | A data "Início" deve ser anterior à data "Final". O sistema deve validar e impedir salvar se inválido                                            |
| RN-018.14 | Cupons com data final passada devem ser automaticamente inativados e marcados com status "Expirado"                                              |
| RN-018.15 | Quando a quantidade máxima é atingida, o cupom deve ser automaticamente inativado                                                                |
| RN-018.16 | Exclusão deve ser soft delete (marcação no banco de dados, não remoção física)                                                                   |
| RN-018.17 | Cupons excluídos não aparecem em nenhuma aba e só podem ser recuperados pela equipe de TI                                                        |
| RN-018.18 | Cupons inativos ou expirados não aparecem como opção de uso para clientes                                                                        |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                      |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-018.01 | Dado que o usuário acessa Detalhes da Atração > Gestão de Cupons, então deve visualizar a lista de cupons na aba "Ativos"                                                     |
| CA-018.02 | Dado que o usuário clica em "Adicionar Cupom", quando preenche os campos obrigatórios e salva, então o cupom deve aparecer na lista                                           |
| CA-018.03 | Dado que o usuário cria um Cupom Agência vinculado à "Agência Silva", quando um turista usa esse cupom, então o uso deve ficar vinculado à agência para controle de comissões |
| CA-018.04 | Dado que o usuário seleciona um cupom e clica em "Gerar link", então deve abrir o modal de QR Code com o link e QR Code gerados                                               |
| CA-018.05 | Dado que o usuário seleciona um cupom e clica em "Compartilhar", quando o link não existe, então o sistema deve gerar o link e abrir WhatsApp para compartilhamento           |
| CA-018.06 | Dado que um cupom tem quantidade máxima de 50 e já foi usado 10 vezes, então o saldo deve exibir 40                                                                           |
| CA-018.07 | Dado que um cupom atinge sua quantidade máxima de usos, então o sistema deve inativar automaticamente o cupom                                                                 |
| CA-018.08 | Dado que a data final de um cupom passa, então o sistema deve inativar automaticamente e marcar como "Expirado"                                                               |
| CA-018.09 | Dado que o usuário tenta salvar um cupom com data "Início" posterior à data "Final", então o sistema deve exibir erro e impedir o salvamento                                  |
| CA-018.10 | Dado que o usuário clica em uma linha da tabela, então deve abrir o modal de visualização com campos somente leitura                                                          |

**Protótipo/Wireframe**

Figura  - WF-021 - Detalhes da Atração/Gestão de Cupons

Figura  - WF-022 - Detalhes da Atração/Gestão de Cupons/Gerar QR Code

Figura  - WF-023 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom

Figura  - WF-024 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom Agencia

### 3.19 Detalhes da Atrações/Gráficos Analytics - Administrador

**ID:** RF-019

**Módulo** : Detalhes da Atração &gt; Gráficos Analytics

**Perfis** : Administrador, Parceiro Comercial

**Prioridade:** Média (Importante)

**Descrição:** O sistema deve exibir um dashboard completo com gráficos e métricas do Google Analytics filtrados pela atração selecionada. Todos os dados são obtidos exclusivamente do Google Analytics, desde que o Parceiro Comercial tenha integrado sua conta do Google Analytics no cadastro (RF-005). Se não houver integração, o sistema deve exibir mensagem solicitando a integração. Os gráficos são interativos e todos são exibidos na mesma tela em formato de grid responsivo.

Requisitos Detalhados

Estrutura da Tela

| ID        | Requisito                                                                                          |
|-----------|----------------------------------------------------------------------------------------------------|
| RF-019.01 | O sistema deve exibir título com o nome da atração selecionada (ex: "Atração Parque Jaime Lerner") |
| RF-019.02 | Todos os gráficos e métricas devem ser exibidos na mesma tela em formato de grid responsivo        |

Filtros de Período

| ID        | Requisito                                                                              |
|-----------|----------------------------------------------------------------------------------------|
| RF-019.03 | O sistema deve exibir botões de filtro rápido: "Tudo", "Hoje", "7 Dias", "30 Dias"     |
| RF-019.04 | O sistema deve exibir opção "Período" para seleção de intervalo de datas personalizado |
| RF-019.05 | O sistema deve atualizar todos os gráficos e métricas ao alterar o filtro de período   |
| RF-019.06 | O filtro padrão ao acessar a tela deve ser "30 Dias"                                   |
| RF-019.07 | O sistema deve manter o filtro selecionado ao recarregar a página                      |

Cards de KPIs (Key Performance Indicators)

| ID        | Requisito                                                                                                                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------|
| RF-019.08 | O sistema deve exibir card "Número de acessos" com valor numérico e indicador de variação percentual (+/-)                   |
| RF-019.09 | O sistema deve exibir card "Usuários únicos" com valor numérico e indicador de variação percentual (+/-)                     |
| RF-019.10 | O sistema deve exibir card "Quantidade vendida" com valor numérico e indicador de variação percentual (+/-)                  |
| RF-019.11 | O sistema deve exibir card "Tempo médio" com valor em formato "Xm Ys" (ex: 16m 44s) e indicador de variação percentual (+/-) |
| RF-019.12 | O sistema deve exibir card "Total vendido" com valor monetário (R$ 0,00) e indicador de variação percentual (+/-)            |
| RF-019.13 | O sistema deve exibir card "Ticket médio" com valor monetário (R$ 0,00) e indicador de variação percentual (+/-)             |
| RF-019.14 | O sistema deve exibir card "Conversão" com valor percentual (%) e indicador de variação percentual (+/-)                     |

Gráficos de Acessos e Visitas

| ID        | Requisito                                                                                                                   |
|-----------|-----------------------------------------------------------------------------------------------------------------------------|
| RF-019.16 | O sistema deve exibir gráfico de barras "Total de visitas" mostrando visitas por horário do dia (0h, 6h, 12h, 18h, 23h)     |
| RF-019.17 | O sistema deve exibir gráfico de barras "Total de ingressos" mostrando ingressos por horário do dia (0h, 6h, 12h, 18h, 23h) |
| RF-019.18 | O sistema deve exibir gráfico de barras "Acessos por horário" mostrando acessos por horário do dia                          |
| RF-019.19 | O sistema deve exibir gráfico de barras "Acessos e qtd de ingressos vendidos por data" mostrando dados por data             |

Gráficos de Estatísticas do Evento

| ID        | Requisito                                                                                                                                                                                           |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-019.20 | O sistema deve exibir gráfico de barras horizontais "Estatísticas do evento acessos" com as métricas: Engajamento do usuário, Acesso a página da atração, Adicionado ao carrinho, Primeiras Visitas |
| RF-019.21 | O gráfico deve exibir valores numéricos para cada métrica                                                                                                                                           |
| RF-019.22 | O gráfico deve ser interativo (hover para ver valores exatos, clicar para ver detalhes)                                                                                                             |

Gráficos Demográficos

| ID        | Requisito                                                                                                                       |
|-----------|---------------------------------------------------------------------------------------------------------------------------------|
| RF-019.23 | O sistema deve exibir gráfico de barras horizontais "Média de acessos por idade" com faixas etárias: 18-24, 24-34, 35-44, 45-54 |
| RF-019.24 | O sistema deve exibir gráfico de rosca (donut) "Acessos por gênero" com distribuição por gênero                                 |
| RF-019.25 | Os gráficos devem ser interativos (hover para ver valores, clicar para filtrar)                                                 |

Gráficos de Vendas e Pagamentos

| ID        | Requisito                                                                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------|
| RF-019.26 | O sistema deve exibir gráfico de rosca (donut) "Vendas por tipo de pagamento" mostrando: Crédito, Pix, Débito |
| RF-019.27 | O gráfico deve exibir percentuais e valores para cada tipo de pagamento                                       |

Gráficos de Origem e Localização

| ID        | Requisito                                                                                                               |
|-----------|-------------------------------------------------------------------------------------------------------------------------|
| RF-019.28 | O sistema deve exibir gráfico de barras horizontais "Acessos por fontes" mostrando origem dos acessos                   |
| RF-019.29 | O sistema deve exibir gráfico de rosca (donut) "Acessos por dispositivo" mostrando distribuição por tipo de dispositivo |
| RF-019.30 | O sistema deve exibir gráfico de barras horizontais "Estados com maior acesso" mostrando os estados com mais acessos    |
| RF-019.31 | O sistema deve exibir gráfico de barras horizontais "Cidades com mais acesso" mostrando as cidades com mais acessos     |

Interatividade dos Gráficos

| ID        | Requisito                                                                                    |
|-----------|----------------------------------------------------------------------------------------------|
| RF-019.32 | Os gráficos devem ser interativos: ao passar o mouse (hover), exibir valores exatos          |
| RF-019.33 | Os gráficos devem permitir clicar em elementos (barras, fatias) para ver detalhes ou filtrar |
| RF-019.34 | O sistema deve exibir tooltips informativos ao interagir com os gráficos                     |

Integração Google Analytics

| ID        | Requisito                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------|
| RF-019.35 | Todos os dados devem ser obtidos exclusivamente do Google Analytics                                      |
| RF-019.36 | O sistema deve filtrar os dados do Google Analytics pelo ID da atração selecionada                       |
| RF-019.37 | Os dados devem ser atualizados com intervalo definido pela equipe de desenvolvimento (não em tempo real) |
| RF-019.38 | O intervalo de atualização não deve prejudicar o desempenho do sistema                                   |

Mensagem de Integração Necessária

| ID        | Requisito                                                                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-019.39 | Se o Parceiro Comercial acessar este menu e não tiver conectado uma conta do Google Analytics, o sistema deve exibir mensagem solicitando a integração |
| RF-019.40 | A mensagem deve incluir instruções de como fazer a integração (link para RF-005 - Perfil)                                                              |
| RF-019.41 | Nenhum gráfico deve ser exibido enquanto não houver integração do Google Analytics                                                                     |

Regras de Negócio

| ID        | Regra                                                                                                    |
|-----------|----------------------------------------------------------------------------------------------------------|
| RN-019.01 | A integração com Google Analytics é obrigatória para visualizar os gráficos                              |
| RN-019.02 | Apenas o Parceiro Comercial dono da atração pode visualizar os dados da sua atração                      |
| RN-019.03 | O Administrador pode visualizar dados de todas as atrações                                               |
| RN-019.04 | Todos os dados são obtidos exclusivamente do Google Analytics (não do banco de dados do sistema)         |
| RN-019.05 | O filtro de período funciona da mesma forma que na tela "Totais da Atração" (RF-004)                     |
| RN-019.06 | A variação percentual compara o período selecionado com o período anterior equivalente                   |
| RN-019.07 | O "Tempo médio" é calculado como tempo médio de permanência na página da atração                         |
| RN-019.08 | A "Conversão" é calculada como: (Ingressos Vendidos / Acessos) × 100                                     |
| RN-019.09 | Os gráficos "Total de visitas" e "Total de ingressos" mostram dados por horário de acesso (não de venda) |
| RN-019.10 | Os dados demográficos (idade, gênero) vêm do Google Analytics                                            |
| RN-019.11 | Os dados de localização (estados, cidades) vêm do Google Analytics                                       |
| RN-019.12 | Os dados de dispositivo e fontes vêm do Google Analytics                                                 |
| RN-019.13 | Os dados de vendas por tipo de pagamento vêm do Google Analytics                                         |
| RN-019.14 | O sistema não oferece opção de exportar os gráficos/dados (PDF, Excel, CSV)                              |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                           |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-019.01 | Dado que o usuário acessa Detalhes da Atração > Gráficos Analytics, quando o Parceiro Comercial tem Google Analytics integrado, então deve visualizar todos os gráficos e métricas |
| CA-019.02 | Dado que o Parceiro Comercial acessa Gráficos Analytics sem ter Google Analytics integrado, então o sistema deve exibir mensagem solicitando a integração                          |
| CA-019.03 | Dado que o usuário altera o filtro de período para "7 Dias", então todos os gráficos e KPIs devem atualizar com dados dos últimos 7 dias                                           |
| CA-019.04 | Dado que o usuário passa o mouse sobre uma barra do gráfico, então deve exibir tooltip com valor exato                                                                             |
| CA-019.05 | Dado que o usuário clica em uma fatia do gráfico "Vendas por tipo de pagamento", então deve exibir detalhes ou filtrar os dados                                                    |
| CA-019.06 | Dado que o período selecionado é "30 Dias", quando os KPIs são calculados, então a variação percentual deve comparar com os 30 dias anteriores                                     |
| CA-019.07 | Dado que o Parceiro Comercial visualiza os gráficos, então deve ver apenas dados da atração selecionada                                                                            |
| CA-019.08 | Dado que o Administrador visualiza os gráficos, então deve ver dados de qualquer atração selecionada                                                                               |
| CA-019.09 | Dado que os dados são atualizados do Google Analytics, então o intervalo de atualização não deve causar lentidão no sistema                                                        |

Protótipo/Wireframe

Figura  - WF-025 - Detalhes da Atração/Gráficos Analytics

### 3.20 Detalhes da Atrações/Editar da Atração - Administrador

**ID:** RF-020

**Módulo:** Detalhes da Atração &gt; Editar Atração

**Perfis com Acesso:** Administrador, Editor, Parceiro Comercial (Editor e Parceiro apenas nas atrações vinculadas)

**Prioridade:** Média (Importante)

**Descrição:** o sistema deverá exibir wizard de 3 etapas da rotina de criação de atrações RF-013, permitindo o Administrador/Parceiro Comercial editar informações da atração.

Requisitos Detalhados

| ID        | Requisito                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-020.01 | O sistema deve exibir o mesmo wizard de 3 etapas do RF-013 em modo edição, ao acessar o submenu "Editar Atração" a partir de Detalhes da Atração (RF-004).                                                                                                                                                                                                                                                                                                                                     |
| RF-020.02 | Os campos editáveis restringem-se às Etapas 1 e 2: Etapa 1 – Foto de Capa, Dados do Evento (Local, CEP, Estado, Cidade, Endereço, Número, Complemento), Sessões do Evento; Etapa 2 – Materiais (Home, Imagem da atração, Fundo), Link de vídeo, Release.                                                                                                                                                                                                                                       |
| RF-020.03 | A Etapa 3 (Dados do Ingresso) não se aplica à rotina Editar Atração.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| RF-020.04 | O sistema deve exibir botões para adicionar, remover e alterar fotos (alterar = substituir o arquivo naquela posição, mantendo as demais).                                                                                                                                                                                                                                                                                                                                                     |
| RF-020.05 | Foto de Capa e materiais (Home, Imagem da atração, Fundo): tamanho máximo 5 MB cada; formatos PNG, JPEG.                                                                                                                                                                                                                                                                                                                                                                                       |
| RF-020.06 | O sistema deve exibir mensagem informativa de que a resolução ideal para foto de capa é 500×500 px (sem bloqueio de upload). RF-020.07 O sistema deve validar que o link de vídeo promocional seja exclusivamente do YouTube (youtube.com ou youtu.be); rejeitar URLs de outros domínios. RF-020.08 O sistema deve permitir apenas um link de vídeo YouTube por atração. RF-020.09 Editor e Parceiro Comercial devem acessar "Editar Atração" somente para atrações às quais estão vinculados. |
| RF-020.07 | O sistema deve validar que o link de vídeo promocional seja exclusivamente do YouTube (youtube.com ou youtu.be); rejeitar URLs de outros domínios.                                                                                                                                                                                                                                                                                                                                             |
| RF-020.08 | O sistema deve permitir apenas um link de vídeo YouTube por atração.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| RF-020.09 | Editor e Parceiro Comercial devem acessar "Editar Atração" somente para atrações às quais estão vinculados.                                                                                                                                                                                                                                                                                                                                                                                    |

Regras de Negócio

| ID        | Regra                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------|
| RN-020.01 | Resolução ideal da foto de capa é 500×500 px; exibir mensagem informativa ao usuário, sem bloquear upload.            |
| RN-020.02 | Limite de 5 MB por foto (capa e materiais). Formatos aceitos: PNG, JPEG.                                              |
| RN-020.03 | Botões adicionar, remover e alterar para cada foto; alterar = substituir arquivo naquela posição, mantendo as demais. |
| RN-020.04 | Link de vídeo promocional deve ser obrigatoriamente do YouTube (youtube.com ou youtu.be).                             |
| RN-020.05 | Apenas um link de vídeo YouTube por atração.                                                                          |
| RN-020.06 | Editor e Parceiro Comercial acessam "Editar Atração" somente para atrações às quais estão vinculados.                 |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                             |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CA-020.01 | Dado que o usuário acessa Detalhes da Atração > Editar Atração, quando a tela abre, então o sistema exibe os mesmos campos do RF-013 (fotos, release, sessões, endereço, link YouTube) em modo edição, Etapas 1 e 2. |
| CA-020.02 | Dado que o usuário envia foto de capa ou material com tamanho > 5 MB, quando confirma, então o sistema exibe mensagem de erro e não aceita o arquivo.                                                                |
| CA-020.03 | Dado que o usuário informa link de vídeo que não seja do YouTube, quando salva, então o sistema exibe mensagem de erro e não salva.                                                                                  |
| CA-020.04 | Dado que o usuário clica em "Alterar" em uma foto e escolhe novo arquivo, quando confirma, então o sistema substitui a foto naquela posição, mantendo as demais.                                                     |
| CA-020.05 | Dado que Editor ou Parceiro Comercial acessa Editar Atração de atração não vinculada, quando tenta acessar, então o sistema impede o acesso ou não exibe a opção.                                                    |
| CA-020.06 | Dado que o sistema exibe mensagem sobre resolução 500×500 para foto de capa, quando o usuário envia foto com outras dimensões, então a mensagem é apenas informativa e o upload não é bloqueado.                     |

### 3.21 Detalhes da Atrações/Usuários - Administrador

**ID:** RF-021

**Módulo** : Gestão de Atrações &gt; Detalhes da Atração &gt; Usuários

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador e Parceiro Comercial o cadastro e a gestão de usuários vinculados a uma atração específica. A tela é acessada pelo menu Detalhes da Atração &gt; Usuários e permite listar os usuários da atração, vincular usuários já cadastrados (perfis Editor, Leitor, Agência e Agente), criar novos usuários Editor ou Leitor no contexto da atração, visualizar, editar e desvincular usuários. Não é permitido vincular ou cadastrar usuários com perfil Parceiro Comercial nem Turista nesta tela.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-021.01 | O sistema deve exibir título e subtítulo da tela no contexto da atração (ex.: "Usuários - [Nome da Atração]").                                                                                                                                                                                                        |
| RF-021.02 | O sistema deve exibir campo de pesquisa por texto (busca por id, nome ou e-mail) para localizar usuários.                                                                                                                                                                                                             |
| RF-021.03 | O sistema deve exibir botão "Filtro" para filtros avançados (ativos, inativos, todos e demais critérios).                                                                                                                                                                                                             |
| RF-021.04 | O sistema deve exibir botão "Adicionar usuário" para vincular usuário existente ou criar novo no contexto da atração.                                                                                                                                                                                                 |
| RF-021.05 | O sistema deve exibir abas para filtrar por status: "Ativos", "Inativos", "Todos".                                                                                                                                                                                                                                    |
| RF-021.06 | O sistema deve exibir a aba "Ativos" selecionada por padrão.                                                                                                                                                                                                                                                          |
| RF-021.07 | O sistema deve exibir tabela com botões de ação (visualizar, editar, desvincular) e colunas: id, nome, e-mail, data de criação, último acesso, ativo.                                                                                                                                                                 |
| RF-021.08 | O sistema deve permitir ordenar as colunas da tabela (ASC/DESC).                                                                                                                                                                                                                                                      |
| RF-021.09 | O sistema deve apresentar filtros para ativos, inativos e todos conforme as abas e o botão Filtro.                                                                                                                                                                                                                    |
| RF-021.10 | Ao incluir novo usuário vinculado à atração, o sistema deve enviar senha provisória por e-mail para o primeiro acesso.                                                                                                                                                                                                |
| RF-021.11 | O sistema deve apresentar barra de pesquisa que permita vincular à atração usuários já cadastrados no sistema com perfil Editor, Leitor, Agência ou Agente; os perfis Parceiro Comercial e Turista não devem estar disponíveis para vínculo ou cadastro nesta tela.                                                   |
| RF-021.12 | O sistema deve exibir, por usuário, botão que permita reenviar ou resetar a senha (ex.: "Resetar senha").                                                                                                                                                                                                             |
| RF-021.13 | O modal de Novo/Editar usuário deve exibir os campos: foto de perfil, Atração (pré-preenchida e somente leitura no contexto), primeiro nome, último nome, CPF/CNPJ, e-mail de contato, telefone, idioma padrão, senha, data de criação, último acesso, perfil (apenas opções Editor, Leitor, Agência, Agente), ativo. |
| RF-021.14 | Ao criar usuário com perfil Editor ou Leitor no contexto da atração, o sistema deve preencher automaticamente os campos Parceiro Comercial e Atração de acordo com a atração em que o usuário está sendo criado.                                                                                                      |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-021.01 | O sistema deve exibir botão que permita reenviar ou resetar a senha caso o usuário não tenha recebido o e-mail com a senha provisória.                                                                        |
| RN-021.02 | Ao criar usuário Editor ou Leitor no contexto da atração, o sistema deve preencher automaticamente o campo Parceiro Comercial e o campo Atração de acordo com a atração em que está sendo criado.             |
| RN-021.03 | Usuários Leitores vinculados à atração têm acesso às rotinas Validar Ingresso e Pesquisar Ingresso.                                                                                                           |
| RN-021.04 | Usuários Editores vinculados à atração têm acesso às rotinas: Validar Ingresso, Pesquisar Ingresso, Editar Atração, Gestão de Ingresso, Categorias, Gestão de Cupons, Totais da Atração e Gráficos Analytics. |
| RN-021.05 | Nesta tela não é permitido vincular nem cadastrar usuários com perfil Parceiro Comercial ou Turista; o dropdown de perfil deve oferecer apenas Editor, Leitor, Agência e Agente.                              |
| RN-021.06 | A ação "Desvincular" remove o vínculo do usuário com a atração; não exclui o usuário do sistema.                                                                                                              |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                      | Resultado Esperado                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| CA-021.01 | Acessar Detalhes da Atração > Usuários como Administrador ou Parceiro Comercial vinculado à atração                                                                                                           | Tela exibida com aba "Ativos" selecionada e tabela de usuários da atração                            |
| CA-021.02 | Dado que o usuário pesquisa por nome ou e-mail, quando digita na barra de pesquisa, então a lista é filtrada pelos usuários vinculados à atração que atendem ao critério                                      | Lista filtrada exibindo apenas usuários da atração que correspondem à busca                          |
| CA-021.03 | Dado que o usuário clica em "Adicionar usuário", quando o modal abre, então o campo Perfil oferece apenas Editor, Leitor, Agência e Agente                                                                    | Dropdown de Perfil não exibe opções Parceiro Comercial nem Turista                                   |
| CA-021.04 | Dado que um novo usuário é incluído na atração, quando o cadastro é salvo, então o sistema envia senha provisória por e-mail ao endereço informado                                                            | E-mail com senha provisória enviado; usuário consegue primeiro acesso com essa senha                 |
| CA-021.05 | Dado que o usuário clica em "Resetar senha" ou equivalente para um usuário vinculado, quando confirma, então o sistema reenvia ou redefine a senha e comunica por e-mail                                      | Senha reenviada ou resetada; e-mail enviado ao usuário                                               |
| CA-021.06 | Dado que Parceiro Comercial cria usuário Editor ou Leitor na atração, quando o modal é aberto, então os campos Parceiro Comercial e Atração estão preenchidos automaticamente com a atração atual             | Campos Parceiro Comercial e Atração exibem valores corretos e não editáveis no contexto              |
| CA-021.07 | Dado que o usuário aciona "Desvincular" para um usuário da atração, quando confirma, então o vínculo é removido e o usuário deixa de aparecer na lista da atração (o usuário permanece cadastrado no sistema) | Usuário removido da listagem da atração; registro de usuário no sistema mantido                      |
| CA-021.08 | Verificar perfis disponíveis no dropdown ao adicionar usuário nesta tela                                                                                                                                      | Apenas Editor, Leitor, Agência e Agente estão disponíveis; Parceiro Comercial e Turista não aparecem |

Protótipo/Wireframe:

Figura  - WF-026 - Detalhes da Atração/Usuários

**Figura  -WF-026 - Detalhes da Atração/Usuários**

Figura  - WF-027 - Detalhes da Atração/Gestão de usuários/Adicionar usuário

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

**ID:** RF-024

**Módulo** : Detalhes da Atração &gt; Gestão Financeira &gt; Resumo das Despesas

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas)

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador e Parceiro Comercial visualizar uma prévia das despesas e receitas por atração, agrupadas por data de liberação, e solicitar adiantamento de repasses.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                                                                            |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.01 | O sistema deve exibir o título "Resumo das Despesas" no topo da página.                                                                                              |
| RF-024.02 | O sistema deve exibir o subtítulo "Condições comerciais do contrato" abaixo do título principal.                                                                     |
| RF-024.03 | O sistema deve exibir a tela no contexto do menu lateral: Detalhes da Atração > Gestão Financeira > Resumo das Despesas.                                             |
| RF-024.04 | O sistema deve exibir apenas as atrações vinculadas ao usuário logado (Administrador visualiza todas; Parceiro Comercial visualiza apenas suas atrações vinculadas). |

Tabela Principal - Resumo por Atração

| ID        | Requisito                                                                                                                                                                         |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.05 | O sistema deve exibir uma tabela principal agrupada por data de liberação contendo as seguintes colunas: Nome (da atração), Status, Data de Liberação, Receita Líquida e Repasse. |
| RF-024.06 | O sistema deve exibir na coluna "Nome" o nome da atração.                                                                                                                         |
| RF-024.07 | O sistema deve exibir na coluna "Status" um dos seguintes valores: "Aguardando Liberação" ou "Recebido".                                                                          |
| RF-024.08 | O sistema deve exibir na coluna "Data de Liberação" a data e hora da liberação no formato DD/MM/AAAA HH:MM:SS.                                                                    |
| RF-024.09 | O sistema deve exibir na coluna "Receita Líquida" o valor calculado da receita líquida da atração formatado como moeda brasileira (R$ X.XXX,XX).                                  |
| RF-024.10 | O sistema deve exibir na coluna "Repasse" um botão "Solicitar Repasse" para cada linha da tabela, quando aplicável.                                                               |
| RF-024.11 | O sistema deve permitir que o usuário clique na linha da tabela principal para expandir ou colapsar os detalhes da atração.                                                       |
| RF-024.12 | O sistema deve exibir visualmente quando uma linha está expandida (ex.: ícone de seta, cor de fundo diferenciada).                                                                |

Tabela Detalhada - Componentes Financeiros

| ID        | Requisito                                                                                                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.13 | O sistema deve exibir uma tabela detalhada abaixo de cada linha expandida da tabela principal contendo os componentes financeiros da atração.                                    |
| RF-024.14 | A tabela detalhada deve conter as seguintes colunas: Nome, Valor, Tipo, Status e Observações.                                                                                    |
| RF-024.15 | O sistema deve exibir na coluna "Nome" os tipos de componente financeiro, tais como: Ingressos, Comissão Agentes, Repasse, Encargos, e outros componentes conforme configurados. |
| RF-024.16 | O sistema deve exibir na coluna "Valor" o valor do componente formatado como moeda brasileira (R$ X.XXX,XX).                                                                     |
| RF-024.17 | O sistema deve exibir na coluna "Tipo" um dos seguintes valores: "Receita" ou "Despesas".                                                                                        |
| RF-024.18 | O sistema deve exibir na coluna "Status" um dos seguintes valores: "Recebido", "Pendente" ou "Bloqueio Financeiro".                                                              |
| RF-024.19 | O sistema deve exibir na coluna "Observações" as observações relacionadas ao componente, ou "" quando não houver observações.                                                    |
| RF-024.20 | O sistema deve calcular e exibir a "Receita Líquida" da tabela principal como a soma das receitas menos a soma das despesas dos componentes financeiros da atração.              |

Modal de Solicitação de Repasse

| ID        | Requisito                                                                                                                                                                                                                                                                                                           |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.21 | O sistema deve exibir um modal quando o usuário clicar no botão "Solicitar Repasse" da tabela principal.                                                                                                                                                                                                            |
| RF-024.22 | O sistema deve exibir no modal uma mensagem informando o valor disponível para repasse no formato "Você tem R$ X.XXX,XX liberados para repasse".                                                                                                                                                                    |
| RF-024.23 | O sistema deve calcular automaticamente o valor disponível para repasse baseado nas seguintes informações financeiras do contrato da atração: Percentual liberado para saque (ou Valor liberado para saque), Valor máximo para saque, Receita líquida disponível, Repasses já solicitados pendentes ou autorizados. |
| RF-024.24 | O sistema deve exibir um campo de entrada "Valor" no modal para que o usuário informe o valor que deseja solicitar como repasse.                                                                                                                                                                                    |
| RF-024.25 | O sistema deve exibir um botão "Valor Total" no modal que, ao ser clicado, preenche automaticamente o campo "Valor" com o valor máximo disponível para repasse.                                                                                                                                                     |
| RF-024.26 | O sistema deve exibir um botão de confirmação (ex.: "Confirmar" ou "Solicitar Repasse") no modal para confirmar a solicitação.                                                                                                                                                                                      |
| RF-024.27 | O sistema deve exibir um botão de cancelamento (ex.: "Cancelar" ou "Fechar") no modal para fechar o modal sem efetuar a solicitação.                                                                                                                                                                                |
| RF-024.28 | O sistema deve validar que o valor informado no campo "Valor" não seja maior que o valor disponível para repasse antes de confirmar a solicitação.                                                                                                                                                                  |
| RF-024.29 | O sistema deve validar que o valor informado no campo "Valor" não seja maior que o valor máximo permitido por solicitação antes de confirmar a solicitação.                                                                                                                                                         |
| RF-024.30 | O sistema deve criar uma nova despesa no registro da atração com o valor solicitado quando o usuário confirmar a solicitação de repasse.                                                                                                                                                                            |
| RF-024.31 | O sistema deve criar uma nova despesa no registro da atração com o valor da taxa de antecipação (obtida das Condições Comerciais do contrato) quando o usuário confirmar a solicitação de repasse.                                                                                                                  |
| RF-024.32 | O sistema deve definir o status inicial das despesas criadas (valor solicitado e taxa de antecipação) como "Pendente" após a solicitação de repasse.                                                                                                                                                                |
| RF-024.33 | O sistema deve atualizar a tabela detalhada automaticamente após a confirmação da solicitação de repasse, incluindo as novas despesas criadas.                                                                                                                                                                      |

Gestão de Status de Repasse

| ID        | Requisito                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-024.34 | O sistema deve permitir que usuários com perfil Administrador alterem o status das despesas de repasse de "Pendente" para "Autorizado".                               |
| RF-024.35 | O sistema deve permitir que usuários com perfil Administrador alterem o status das despesas de repasse de "Autorizado" para "Recebido" quando o repasse for efetuado. |
| RF-024.36 | O sistema deve atualizar automaticamente a tabela principal e detalhada quando houver alteração de status das despesas de repasse.                                    |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                                                                                                                                                |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-024.01 | O valor disponível para repasse deve ser calculado considerando: (Receita Líquida × Percentual liberado para saque) OU Valor liberado para saque (conforme configuração nas Informações Financeiras), limitado ao Valor máximo para saque, menos os repasses já solicitados com status "Pendente" ou "Autorizado".                                                   |
| RN-024.02 | O valor máximo permitido por solicitação de repasse é o Valor máximo para saque definido nas Informações Financeiras do contrato da atração.                                                                                                                                                                                                                         |
| RN-024.03 | O usuário não pode solicitar um novo repasse antes de aguardar o prazo de pagamento desde a última solicitação. O prazo é calculado a partir da data da última solicitação de repasse com status "Recebido" ou a partir da data de liberação, conforme o maior entre "Prazo pagamento" (Condições Comerciais) e "Tempo mínimo para saque" (Informações Financeiras). |
| RN-024.04 | O campo "Valor" no modal de solicitação de repasse é obrigatório e deve ser maior que zero.                                                                                                                                                                                                                                                                          |
| RN-024.05 | O valor informado no campo "Valor" não pode ser maior que o valor disponível para repasse exibido na mensagem do modal.                                                                                                                                                                                                                                              |
| RN-024.06 | O valor informado no campo "Valor" não pode ser maior que o valor máximo permitido por solicitação (Valor máximo para saque).                                                                                                                                                                                                                                        |
| RN-024.07 | A taxa de antecipação deve ser obtida do campo "Tx. Antecipação" das Condições Comerciais do contrato da atração.                                                                                                                                                                                                                                                    |
| RN-024.08 | Quando uma solicitação de repasse é confirmada, o sistema deve criar duas despesas: uma com o valor solicitado e outra com o valor da taxa de antecipação calculada sobre o valor solicitado.                                                                                                                                                                        |
| RN-024.09 | O status "Bloqueio Financeiro" deve ser exibido quando houver alguma restrição financeira que impeça o repasse, conforme definido nas observações do componente.                                                                                                                                                                                                     |
| RN-024.10 | Apenas usuários com perfil Administrador podem alterar o status das despesas de repasse de "Pendente" para "Autorizado" e de "Autorizado" para "Recebido".                                                                                                                                                                                                           |
| RN-024.11 | O agrupamento por data de liberação deve agrupar as atrações que possuem a mesma data de liberação. Quando todas as atrações têm a mesma data, não é necessário exibir cabeçalho de grupo visível.                                                                                                                                                                   |
| RN-024.12 | O Parceiro Comercial pode visualizar e solicitar repasse apenas para atrações vinculadas ao seu contrato.                                                                                                                                                                                                                                                            |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                                                                            | Resultado Esperado                                                     |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
| CA-024.01 | Dado que um usuário Administrador acessa a tela Resumo das Despesas, quando visualizar a tabela principal, então o sistema deve exibir todas as atrações agrupadas por data de liberação com as colunas Nome, Status, Data de Liberação, Receita Líquida e Repasse. | Tabela principal exibe todas as atrações com as colunas especificadas. |
| CA-024.02 | Dado que um usuário Parceiro Comercial acessa a tela Resumo das Despesas, quando visualizar a tabela principal, então o sistema deve exibir apenas as atrações vinculadas ao seu contrato.                                                                          | Tabela principal exibe apenas atrações do Parceiro Comercial.          |
| CA-024.03 | Dado que o usuário clica em uma linha da tabela principal, quando a linha estiver colapsada, então o sistema deve expandir e exibir a tabela detalhada com os componentes financeiros da atração.                                                                   | Tabela detalhada é exibida abaixo da linha clicada.                    |
| CA-024.04 | Dado que o usuário clica no botão "Solicitar Repasse", quando o modal for exibido, então o sistema deve mostrar o valor disponível para repasse calculado corretamente baseado nas Informações Financeiras do contrato.                                             | Modal exibe valor disponível calculado corretamente.                   |
| CA-024.05 | Dado que o usuário clica no botão "Valor Total" no modal, quando o botão for acionado, então o sistema deve preencher o campo "Valor" com o valor máximo disponível para repasse.                                                                                   | Campo Valor é preenchido automaticamente com o valor máximo.           |
| CA-024.06 | Dado que o usuário informa um valor maior que o disponível no campo "Valor" do modal, quando tentar confirmar a solicitação, então o sistema deve exibir mensagem de erro e impedir a confirmação.                                                                  | Sistema valida e impede confirmação com valor inválido.                |
| CA-024.07 | Dado que o usuário confirma uma solicitação de repasse válida, quando a solicitação for processada, então o sistema deve criar duas despesas (valor solicitado e taxa de antecipação) com status "Pendente" e atualizar a tabela detalhada.                         | Duas despesas são criadas e tabela é atualizada.                       |
| CA-024.08 | Dado que um usuário Administrador altera o status de uma despesa de repasse de "Pendente" para "Autorizado", quando a alteração for confirmada, então o sistema deve atualizar o status na tabela detalhada.                                                        | Status é atualizado na tabela detalhada.                               |
| CA-024.09 | Dado que o usuário tenta solicitar um novo repasse antes de aguardar o prazo de pagamento, quando tentar acessar o modal, então o sistema deve impedir a solicitação ou exibir mensagem informando o prazo restante.                                                | Sistema valida prazo e impede ou informa prazo restante.               |
| CA-024.10 | Dado que uma atração possui receita líquida de R$ 100.000,00 e percentual liberado para saque de 50%, quando o sistema calcular o valor disponível, então deve exibir R$ 50.000,00 (ou o valor máximo para saque, se menor).                                        | Cálculo do valor disponível está correto.                              |

Ex.

| Dados                            | Valor         |
|----------------------------------|---------------|
| Percentual liberado para saque   | 50%           |
| Valor máximo liberado para saque | R$ 10.000,00  |
| Receita líquida                  | R$ 100.000,00 |
| Prazo para pagamento             | 15 dias       |

Protótipo/Wireframe

Figura  - WF-030 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Resumo das Despesas

### 3.25 Detalhes da Atrações/Tela de Validação de Ingressos

**ID:** RF-025

**Módulo** : Detalhes da Atração &gt; Validação de Ingressos

**Perfis com Acesso** : Administrador, Parceiro Comercial (apenas nas atrações vinculadas), Leitor

**Prioridade:** Alta (Essencial)

**Descrição:** O sistema deve permitir aos usuários Administrador, Parceiro Comercial e Leitor validar ingressos de turistas através da leitura de QR Code utilizando a câmera do dispositivo.

Requisitos Detalhados

Estrutura Geral da Tela

| ID        | Requisito                                                                                                   |
|-----------|-------------------------------------------------------------------------------------------------------------|
| RF-025.01 | O sistema deve exibir o título "Validar Ingressos" no topo da página.                                       |
| RF-025.02 | O sistema deve exibir o subtítulo "Histórico de ingressos validados" abaixo do título principal.            |
| RF-025.03 | O sistema deve exibir a tela no contexto do menu lateral: Detalhes da Atração > Validar Ingressos.          |
| RF-025.04 | O sistema deve exibir o contexto da atração (nome e localização) no topo da barra lateral quando aplicável. |
| RF-025.05 | O sistema deve exibir apenas os ingressos da atração selecionada no contexto de Detalhes da Atração.        |
| RF-025.06 | O Parceiro Comercial deve visualizar apenas ingressos das atrações vinculadas ao seu contrato.              |
| RF-025.07 | O Leitor deve visualizar apenas ingressos das atrações às quais está vinculado.                             |

Barra de Ferramentas

| ID        | Requisito                                                                                                                                             |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.08 | O sistema deve exibir um campo de busca no topo da tela para pesquisar ingressos por ID, nome do titular ou e-mail.                                   |
| RF-025.09 | O sistema deve exibir um botão "Filtro" com ícone de funil no topo da tela para aplicar filtros aos ingressos exibidos.                               |
| RF-025.10 | O sistema deve exibir um botão "Iniciar Validação" com ícone de câmera no topo da tela para iniciar o processo de validação de um novo ingresso.      |
| RF-025.11 | O sistema deve permitir que o usuário digite termos de busca no campo de pesquisa e atualize a lista de ingressos em tempo real conforme a digitação. |

Abas de Status

| ID        | Requisito                                                                                                                 |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
| RF-025.12 | O sistema deve exibir três abas abaixo da barra de ferramentas: "Todos", "Validados" e "Cancelados".                      |
| RF-025.13 | O sistema deve exibir a aba "Todos" como ativa por padrão ao carregar a tela.                                             |
| RF-025.14 | O sistema deve permitir que o usuário clique em uma aba para filtrar os ingressos exibidos conforme o status selecionado. |
| RF-025.15 | O sistema deve exibir visualmente qual aba está ativa (ex.: sublinhado, cor diferenciada).                                |
| RF-025.16 | A aba "Todos" deve exibir todos os ingressos independente do status.                                                      |
| RF-025.17 | A aba "Validados" deve exibir apenas ingressos com status "Validado".                                                     |
| RF-025.18 | A aba "Cancelados" deve exibir apenas ingressos com status "Cancelado" ou "Erro de leitura".                              |

Tabela de Histórico de Ingressos

| ID        | Requisito                                                                                                                                                              |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.19 | O sistema deve exibir uma tabela com o histórico de ingressos validados contendo as seguintes colunas: ID Ingresso, Nome, Status, Data/hora da Leitura e Validado por. |
| RF-025.20 | O sistema deve exibir na coluna "ID Ingresso" o número de identificação único do ingresso.                                                                             |
| RF-025.21 | O sistema deve exibir um ícone de documento ao lado do ID do ingresso indicando que é possível copiar o ID.                                                            |
| RF-025.22 | O sistema deve permitir que o usuário clique no ícone de documento ou no ID do ingresso para copiar o ID para a área de transferência.                                 |
| RF-025.23 | O sistema deve exibir feedback visual quando o ID for copiado com sucesso (ex.: mensagem temporária "ID copiado").                                                     |
| RF-025.24 | O sistema deve exibir na coluna "Nome" o nome completo do titular do ingresso na primeira linha e o e-mail do titular na segunda linha (formato de duas linhas).       |
| RF-025.25 | O sistema deve exibir na coluna "Status" um badge/botão visual com o status da validação.                                                                              |
| RF-025.26 | O sistema deve exibir o status "Validado" em um badge de cor azul escuro quando o ingresso foi validado com sucesso.                                                   |
| RF-025.27 | O sistema deve exibir o status "Erro de leitura" em um badge de cor cinza claro quando houve erro na leitura do QR Code.                                               |
| RF-025.28 | O sistema deve exibir o status "Cancelado" em um badge de cor cinza claro quando o ingresso foi cancelado.                                                             |
| RF-025.29 | O sistema deve exibir na coluna "Data/hora da Leitura" a data e hora em que o ingresso foi lido/validado no formato DD/MM/AAAA HH:MM:SS.                               |
| RF-025.30 | O sistema deve exibir na coluna "Validado por" o nome do usuário (Leitor, Administrador ou Parceiro Comercial) que realizou a validação do ingresso.                   |
| RF-025.31 | O sistema deve permitir ordenação ascendente ou descendente em todas as colunas da tabela através de setas de ordenação.                                               |

Paginação

| ID        | Requisito                                                                                                                                                                                               |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.33 | O sistema deve exibir controles de paginação na parte inferior da tabela quando houver mais ingressos do que o limite de itens por página.                                                              |
| RF-025.34 | O sistema deve exibir um seletor (dropdown) para escolher o número de itens exibidos por página (ex.: 10, 25, 50, 100).                                                                                 |
| RF-025.35 | O sistema deve exibir botões de navegação: primeira página ("<<"), página anterior ("<"), próxima página (">") e última página (">>").                                                                  |
| RF-025.36 | O sistema deve exibir informações sobre a paginação no formato "X a Y de Z" (ex.: "1 a 10 de 200"), onde X é o primeiro item da página atual, Y é o último item da página atual e Z é o total de itens. |
| RF-025.37 | O sistema deve atualizar a tabela automaticamente quando o usuário alterar o número de itens por página ou navegar entre páginas.                                                                       |

Processo de Validação de Ingressos

| ID        | Requisito                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RF-025.38 | O sistema deve exibir um modal ou tela de validação quando o usuário clicar no botão "Iniciar Validação".                                                             |
| RF-025.39 | O sistema deve solicitar permissão de acesso à câmera do dispositivo quando o usuário iniciar a validação.                                                            |
| RF-025.40 | O sistema deve exibir mensagem informativa se o usuário negar permissão de acesso à câmera, explicando que a câmera é necessária para validar ingressos.              |
| RF-025.41 | O sistema deve exibir a visualização da câmera em tempo real quando a permissão for concedida.                                                                        |
| RF-025.42 | O sistema deve processar automaticamente o QR Code quando ele for detectado na visualização da câmera.                                                                |
| RF-025.43 | O sistema deve validar se o QR Code lido corresponde a um ingresso válido da atração atual.                                                                           |
| RF-025.44 | O sistema deve verificar se o ingresso não foi cancelado antes de permitir a validação.                                                                               |
| RF-025.45 | O sistema deve verificar se o ingresso não foi já validado anteriormente antes de permitir uma nova validação.                                                        |
| RF-025.46 | O sistema deve exibir feedback visual imediato após a leitura do QR Code indicando sucesso ou erro na validação.                                                      |
| RF-025.47 | O sistema deve exibir mensagem de sucesso quando o ingresso for validado com sucesso (ex.: "Ingresso validado com sucesso!").                                         |
| RF-025.48 | O sistema deve exibir mensagem de erro quando o ingresso estiver cancelado (ex.: "Ingresso cancelado. Entrada bloqueada.").                                           |
| RF-025.49 | O sistema deve exibir mensagem de erro quando houver erro na leitura do QR Code (ex.: "Erro na leitura do QR Code. Tente novamente.").                                |
| RF-025.50 | O sistema deve exibir mensagem de erro quando o ingresso já foi validado anteriormente (ex.: "Ingresso já foi validado anteriormente.").                              |
| RF-025.51 | O sistema deve registrar no histórico a validação realizada, incluindo: ID do ingresso, data/hora da leitura, status da validação e usuário que realizou a validação. |
| RF-025.52 | O sistema deve atualizar automaticamente a tabela de histórico após uma validação bem-sucedida ou com erro.                                                           |
| RF-025.53 | O sistema deve permitir que o usuário feche o modal/tela de validação e retorne à lista de histórico.                                                                 |

Regras de Negócio

| ID        | Regra                                                                                                                                                                                                                                              |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| RN-025.01 | Ao clicar no botão "Iniciar Validação", o sistema deve solicitar permissão de acesso à câmera do dispositivo. Se a permissão for negada, o sistema deve exibir mensagem informativa e não permitir a validação até que a permissão seja concedida. |
| RN-025.02 | O sistema deve bloquear a entrada (não permitir validação) quando o ingresso estiver com status "Cancelado".                                                                                                                                       |
| RN-025.03 | O sistema deve bloquear a entrada (não permitir validação) quando houver erro na leitura do QR Code (QR Code inválido, corrompido ou não reconhecido).                                                                                             |
| RN-025.04 | O sistema deve permitir apenas uma validação por ingresso. Se um ingresso já foi validado anteriormente, o sistema deve exibir mensagem informando que o ingresso já foi validado e não permitir nova validação.                                   |
| RN-025.05 | O QR Code lido deve corresponder a um ingresso válido da atração atual. Se o QR Code pertencer a outra atração, o sistema deve exibir mensagem de erro.                                                                                            |
| RN-025.06 | A busca deve ser realizada em tempo real, filtrando os resultados conforme o usuário digita no campo de pesquisa. A busca deve considerar ID do ingresso, nome do titular e e-mail.                                                                |
| RN-025.07 | Os filtros devem permitir filtrar por: data/hora da leitura (período), status (Validado, Cancelado, Erro de leitura), validado por (nome do usuário), e outros critérios conforme necessário.                                                      |
| RN-025.08 | A ordenação das colunas deve ser persistente durante a sessão do usuário, mas não deve ser salva entre sessões diferentes.                                                                                                                         |
| RN-025.09 | O número padrão de itens por página deve ser 10, mas o usuário pode alterar para 25, 50 ou 100 itens por página.                                                                                                                                   |
| RN-025.10 | O Administrador pode visualizar e validar ingressos de todas as atrações do sistema.                                                                                                                                                               |
| RN-025.11 | O Parceiro Comercial pode visualizar e validar ingressos apenas das atrações vinculadas ao seu contrato.                                                                                                                                           |
| RN-025.12 | O Leitor pode visualizar e validar ingressos apenas das atrações às quais está vinculado através do cadastro de usuários da atração (RF-021).                                                                                                      |
| RN-025.13 | A data/hora da leitura deve ser registrada no momento exato em que o QR Code é lido com sucesso, utilizando o horário do servidor.                                                                                                                 |
| RN-025.14 | O campo "Validado por" deve registrar o nome completo do usuário logado que realizou a validação, não apenas o perfil.                                                                                                                             |

Critérios de Aceitação

| ID        | Critério                                                                                                                                                                                                                                                         | Resultado Esperado                                                                |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| CA-025.01 | Dado que um usuário Administrador acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir o histórico de todos os ingressos validados da atração com as colunas ID Ingresso, Nome, Status, Data/hora da Leitura e Validado por. | Tabela exibe todos os ingressos da atração com as colunas especificadas.          |
| CA-025.02 | Dado que um usuário Parceiro Comercial acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir apenas ingressos das atrações vinculadas ao seu contrato.                                                                        | Tabela exibe apenas ingressos do Parceiro Comercial.                              |
| CA-025.03 | Dado que um usuário Leitor acessa a tela Validar Ingressos, quando visualizar a tabela, então o sistema deve exibir apenas ingressos das atrações às quais está vinculado.                                                                                       | Tabela exibe apenas ingressos das atrações vinculadas ao Leitor.                  |
| CA-025.04 | Dado que o usuário clica no botão "Iniciar Validação", quando a permissão de câmera for solicitada e concedida, então o sistema deve exibir a visualização da câmera em tempo real.                                                                              | Visualização da câmera é exibida em tempo real.                                   |
| CA-025.05 | Dado que o usuário escaneia um QR Code válido de um ingresso não cancelado e não validado anteriormente, quando o QR Code for lido, então o sistema deve validar o ingresso com sucesso, registrar no histórico e atualizar a tabela automaticamente.            | Ingresso é validado, registrado no histórico e tabela é atualizada.               |
| CA-025.06 | Dado que o usuário escaneia um QR Code de um ingresso cancelado, quando o QR Code for lido, então o sistema deve bloquear a entrada, exibir mensagem "Ingresso cancelado. Entrada bloqueada." e registrar no histórico com status "Cancelado".                   | Entrada é bloqueada, mensagem é exibida e registro é criado com status Cancelado. |
| CA-025.07 | Dado que o usuário escaneia um QR Code inválido ou corrompido, quando o QR Code for lido, então o sistema deve exibir mensagem "Erro na leitura do QR Code. Tente novamente." e registrar no histórico com status "Erro de leitura".                             | Mensagem de erro é exibida e registro é criado com status Erro de leitura.        |
| CA-025.08 | Dado que o usuário tenta validar um ingresso já validado anteriormente, quando o QR Code for lido, então o sistema deve exibir mensagem "Ingresso já foi validado anteriormente." e não permitir nova validação.                                                 | Mensagem é exibida e nova validação é bloqueada.                                  |
| CA-025.09 | Dado que o usuário clica no ícone de documento ao lado do ID do ingresso, quando o clique for realizado, então o sistema deve copiar o ID para a área de transferência e exibir feedback visual "ID copiado".                                                    | ID é copiado e feedback visual é exibido.                                         |
| CA-025.10 | Dado que o usuário digita um termo no campo de busca, quando o termo for digitado, então o sistema deve filtrar a lista de ingressos em tempo real, exibindo apenas os ingressos que correspondem ao termo pesquisado (ID, nome ou e-mail).                      | Lista é filtrada em tempo real conforme a digitação.                              |
| CA-025.11 | Dado que o usuário clica na aba "Validados", quando a aba for selecionada, então o sistema deve exibir apenas ingressos com status "Validado" na tabela.                                                                                                         | Tabela exibe apenas ingressos validados.                                          |
| CA-025.12 | Dado que o usuário clica em uma coluna da tabela para ordenar, quando a ordenação for aplicada, então o sistema deve reorganizar os ingressos conforme a ordenação selecionada (ascendente ou descendente) e exibir visualmente a coluna ordenada.               | Ingressos são reorganizados e coluna ordenada é destacada visualmente.            |

Protótipo/Wireframe

Figura  - WF-031 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Validar Ingressos

## 4 Requisitos Não Funcionais

### 4.1 Desempenho

Upload de até 8 fotos de 5MB cada

Tempo de resposta &lt; 5 segundos

Suporte a 30 usuários simultâneos

### 4.2 Usabilidade

Campos obrigatórios destacados

Feedback visual imediato

### 4.3 Segurança

Autenticação com senha criptografada

Controle de acesso por perfil

Criptografia de dados sensíveis

Logout automático após 15 minutos

### 4.4 Portabilidade e Compatibilidade

Compatibilidade Android 9+ e iOS 13+

### 4.5 Confiabilidade e Disponibilidade

Integridade de dados em caso de falha

### 4.6 Manutenibilidade e Evolução

Arquitetura modular

### 4.7 Armazenamento e Dados

Compressão de imagens (500 KB, 720x720px)

Backup automático diário

## 5 Casos de Uso

### 5.1 CU-001 - Realizar Login

ID: CU-001

Nome: Realizar Login

Ator Principal: Usuário (todos os perfis: Administrador, Parceiro Comercial, Editor, Leitor, Agência, Agente)

Atores Secundários: Sistema (validação de credenciais)

Pré-condições: Usuário cadastrado no sistema; e-mail e senha registrados

Pós-condições: Usuário autenticado no sistema; redirecionado para a tela inicial conforme perfil

Requisitos Relacionados: RF-001

Fluxo Principal:

1. O ator acessa a tela de login do Backoffice.

O ator informa e-mail e senha.

O sistema valida as credenciais.

O sistema redireciona o ator para a tela inicial (home) de acordo com o perfil de acesso.

Fluxos de Exceção:

3a. Credenciais inválidas: Sistema exibe mensagem de erro e mantém na tela de login.
3b. Usuário inativo: Sistema exibe mensagem informando que o usuário está inativo.

### 5.2 CU-002 - Realizar Logout

ID: CU-002

Nome: Realizar Logout

Ator Principal: Usuário autenticado

Atores Secundários: Sistema

Pré-condições: Usuário autenticado no sistema

Pós-condições: Sessão encerrada; usuário redirecionado para a tela de login

Requisitos Relacionados: RF-001

Fluxo Principal:

1. O ator clica na opção de logout (menu ou botão).
2. O sistema encerra a sessão.
3. O sistema redireciona o ator para a tela de login.

### 5.3 CU-003 - Recuperar Senha

ID: CU-003

Nome: Recuperar Senha

Ator Principal: Usuário

Atores Secundários: Sistema (envio de e-mail)

Pré-condições: E-mail cadastrado no sistema

Pós-condições: Usuário com nova senha definida

Requisitos Relacionados: RF-001

Fluxo Principal:

1. O ator acessa a tela de login e clica em "Esqueci minha senha".
2. O sistema exibe campo para informar o e-mail.
3. O ator informa o e-mail de cadastro.
4. O sistema envia link ou senha temporária para o e-mail.
5. O ator acessa o link ou insere a senha temporária e define nova senha.
6. O sistema confirma a alteração e redireciona para a tela de login.

Fluxos de Exceção:

4a. E-mail não cadastrado: Sistema exibe mensagem genérica ou informa que o e-mail não foi encontrado.

### 5.4 CU-004 - Visualizar Dashboard

ID: CU-004

Nome: Visualizar Dashboard

Ator Principal: Administrador, Parceiro Comercial
Atores Secundários: —

Pré-condições: Usuário autenticado com perfil Administrador ou Parceiro Comercial

Pós-condições: Dashboard exibido com indicadores e menu conforme perfil

Requisitos Relacionados: RF-002, RF-003

Fluxo Principal:

1. O ator autenticado acessa o sistema.
2. O sistema exibe a tela inicial (Dashboard) com menu lateral e indicadores consolidados (vendas, atrações, métricas), conforme perfil.
3. O ator visualiza os cards e opções de menu disponíveis.

### 5.5 CU-005 - Gerenciar Perfil

ID: CU-005

Nome: Gerenciar Perfil

Ator Principal: Usuário autenticado

Atores Secundários: —

Pré-condições: Usuário autenticado

Pós-condições: Dados do perfil atualizados no sistema; integração Google

Analytics (Parceiro) salva quando aplicável

Requisitos Relacionados: RF-005

Fluxo Principal:

1. O ator acessa o modal de perfil (menu ou ícone).
2. O sistema exibe os dados atuais (nome, e-mail, etc.) e opções exclusivas por perfil.
3. O ator altera os campos desejados e confirma.
4. O sistema valida e salva as alterações.
5. O sistema exibe confirmação de sucesso.

Fluxos de Exceção:

4a. Dados inválidos: Sistema exibe mensagem de validação e mantém o modal aberto.

### 5.6 CU-006 - Cadastrar Usuário

ID: CU-006

Nome: Cadastrar Usuário

Ator Principal: Administrador

Pré-condições: Usuário autenticado com perfil Administrador

Pós-condições: Novo usuário cadastrado no sistema com perfil e dados definidos

Requisitos Relacionados: RF-007

Fluxo Principal:

1. O ator acessa Gestão de Usuários e clica em adicionar/cadastrar usuário.
2. O sistema exibe o modal de cadastro com campos comuns e campos dinâmicos por perfil.
3. O ator preenche os dados e seleciona o perfil.
4. O ator preenche os campos obrigatórios e confirma.
5. O sistema valida (e-mail único, etc.) e salva o usuário.
6. O sistema exibe confirmação e atualiza a lista.

Fluxos de Exceção:

5a. E-mail já cadastrado: Sistema exibe mensagem de erro e mantém o modal.
5b. Campos obrigatórios faltando: Sistema exibe validação e impede o salvamento.

### 5.7 CU-007 - Editar Usuário

ID: CU-007

Nome: Editar Usuário

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador; usuário a editar existente

Pós-condições: Dados do usuário atualizados no sistema

Requisitos Relacionados: RF-007

Fluxo Principal:

1. O ator acessa Gestão de Usuários, seleciona um usuário e clica em Editar.
2. O sistema exibe o modal em modo edição com dados preenchidos.
3. O ator altera os campos desejados e confirma.
4. O sistema valida e salva.
5. O sistema exibe confirmação e atualiza a lista.

Fluxos de Exceção:

4a. Validação falha: Sistema exibe mensagem e mantém o modal.

### 5.8 CU-008 - Gerenciar Contratos

ID: CU-008

Nome: Gerenciar Contratos

Ator Principal: Administrador

Atores Secundários: Sistema (integração Docusign)

Pré-condições: Usuário autenticado como Administrador

Pós-condições: Contratos visualizados, criados, editados ou enviados para assinatura conforme ação

Requisitos Relacionados: RF-008

Fluxo Principal:

1. O ator acessa Gestão de Contratos.

O sistema exibe a tabela de Parceiros Comerciais com opção de expandir contratos por atração.

O ator expande um parceiro e visualiza os contratos.

O ator pode selecionar contratos e executar ações (enviar para Docusign, editar, etc.).

O sistema processa a ação e atualiza status.

### 5.9 CU-009 - Cadastrar Condições Comerciais

ID: CU-009

Nome: Cadastrar Condições Comerciais

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador

Pós-condições: Condição comercial cadastrada e disponível para vínculo em contratos

Requisitos Relacionados: RF-010

Fluxo Principal:

1. O ator acessa Configurações Comerciais &gt; Condições Comerciais.

O ator clica em Nova Condição Comercial.

O sistema exibe o modal com campos.

O ator preenche os dados e confirma.

O sistema valida e salva.

O sistema exibe confirmação e atualiza a tabela.

### 5.10 CU-010 - Cadastrar Informações Financeiras

ID: CU-010

Nome: Cadastrar Informações Financeiras

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador

Pós-condições: Informação financeira cadastrada e disponível para vínculo em contratos

Requisitos Relacionados: RF-011

Fluxo Principal:

1. O ator acessa Configurações Comerciais &gt; Informações Financeiras.
2. O ator clica em Nova Informação Financeira.
3. O sistema exibe o modal com campos.
4. O ator preenche e confirma.
5. O sistema valida e salva.
6. O sistema exibe confirmação e atualiza a tabela.

### 5.11 CU-011 - Cadastrar Atração

ID: CU-011

Nome: Cadastrar Atração

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador (ou Parceiro Comercial conforme RF-013)

Pós-condições: Nova atração cadastrada (rascunho ou ativa)

Requisitos Relacionados: RF-013

Fluxo Principal:

1. O ator acessa Gestão de Atrações e clica em Adicionar Atração.
2. O sistema exibe o modal em 3 etapas (Dados da Atração; Dados Bancários e Materiais; Dados do Ingresso).
3. O ator preenche as etapas e conclui ou salva como rascunho.
4. O sistema valida e salva; exibe confirmação.

### 5.12 CU-012 - Editar Atração

ID: CU-012

Nome: Editar Atração

Ator Principal: Administrador, Parceiro Comercial, Editor

Pré-condições: Usuário autenticado com perfil com permissão; atração existente

Pós-condições: Dados da atração atualizados (Etapas 1 e 2)

Requisitos Relacionados: RF-006, RF-007, RF-013

Fluxo Principal:

1. O ator acessa Detalhes da Atração e seleciona Editar Atração.
2. O sistema exibe o modal em modo edição com Etapas 1 e 2.
3. O ator altera os campos desejados e salva.
4. O sistema valida e salva.
5. O sistema exibe confirmação.

### 5.13 CU-013 - Visualizar Atrações no Mapa

ID: CU-013

Nome: Visualizar Atrações no Mapa

Ator Principal: Turista

Pré-condições: Acesso ao portal público

Pós-condições: Atrações exibidas no mapa conforme filtros

Requisitos Relacionados: RF-003

Fluxo Principal:

1. O ator acessa o portal público e a funcionalidade de mapa/rotas.
2. O sistema exibe o mapa com as atrações disponíveis.
3. O ator pode filtrar ou clicar em uma atração para ver detalhes.

### 5.14 CU-014 - Criar Pacote de Ingressos

ID: CU-014

Nome: Criar Pacote de Ingressos

Ator Principal: Administrador, Parceiro Comercial

Pré-condições: Usuário autenticado com perfil com permissão; atrações e ingressos configurados

Pós-condições: Pacote de ingressos criado e disponível para venda

Requisitos Relacionados: RF-010

Fluxo Principal:

1. O ator acessa a funcionalidade de pacotes de ingressos.
2. O sistema exibe a tela de criação de pacote.
3. O ator define atrações/ingressos incluídos, preço e condições.
4. O ator confirma.
5. O sistema valida e salva o pacote.
6. O sistema exibe confirmação.

### 5.15 CU-015 - Visualizar Totais da Atração

ID: CU-015

Nome: Visualizar Totais da Atração

Ator Principal: Administrador, Parceiro Comercial, Editor, Leitor

Pré-condições: Usuário autenticado; com acesso à atração

Pós-condições: Tela de totais exibida com indicadores e filtros de período

Requisitos Relacionados: RF-004 (Detalhes da Atração / Totais)

Fluxo Principal:

1. O ator acessa Detalhes da Atração (via Dashboard ou menu Gestão de Atrações).
2. O sistema exibe a tela de Totais com cards (Ingressos Vendidos, Emitidos, Reservados, Validação).
3. O ator pode aplicar filtros de período e visualizar os indicadores.

### 5.16 CU-016 - Gerenciar Categorias da Atração

ID: CU-016

Nome: Gerenciar Categorias da Atração

Ator Principal: Administrador, Parceiro Comercial, Editor

Pré-condições: Usuário autenticado com permissão; atração selecionada

Pós-condições: Categorias de ingresso criadas/editadas/removidas

Requisitos Relacionados: RF-014, WF-016

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Categorias.
2. O sistema exibe a tabela de categorias com abas e ações.
3. O ator adiciona, edita ou remove categorias.
4. O sistema valida e salva; atualiza a tabela.

### 5.17 CU-017 - Pesquisar Ingresso

ID: CU-017

Nome: Pesquisar Ingresso

Ator Principal: Administrador, Parceiro Comercial, Editor, Leitor

Pré-condições: Usuário autenticado; acesso à atração no contexto Detalhes da Atração

Pós-condições: Lista de ingressos exibida conforme busca e filtros

Requisitos Relacionados: RF-015, WF-017, WF-018

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Pesquisar Ingresso.
2. O sistema exibe a tabela de ingressos com abas, busca e filtros.
3. O ator informa critérios de busca/filtro.
4. O sistema atualiza a lista de ingressos.
5. O ator pode executar ações (validar, reenviar, visualizar QR Code, cancelar) ou ver detalhes.

### 5.18 CU-018 - Gerenciar Ingressos da Atração

ID: CU-018

Nome: Gerenciar Ingressos da Atração

Ator Principal: Administrador, Parceiro Comercial, Editor

Pré-condições: Usuário autenticado com permissão; atração selecionada; categorias existentes

Pós-condições: Lotes de ingresso criados/editados

Requisitos Relacionados: RF-017, WF-019, WF-020

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Gestão de Ingressos.
2. O sistema exibe a tabela de ingressos (lotes).
3. O ator clica em Adicionar Ingresso.
4. O sistema exibe o modal com campos.
5. O ator preenche e salva.
6. O sistema valida e salva; atualiza a tabela.

### 5.19 CU-019 - Gerenciar Cupons da Atração

ID: CU-019

Nome: Gerenciar Cupons da Atração

Ator Principal: Administrador, Parceiro Comercial, Editor

Pré-condições: Usuário autenticado com permissão; atração selecionada

Pós-condições: Cupons normais ou de agência criados/editados

Requisitos Relacionados: RF-018, WF-021 a WF-024

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Gestão de Cupons.
2. O sistema exibe a tabela de cupons com abas, busca e filtros.
3. O ator adiciona cupom normal ou cupom agência.
4. O ator define tipo de desconto (%), valor fixo, quantidade máxima de usos, validade, categorias aplicáveis.
5. O sistema valida e salva; atualiza a tabela.

### 5.20 CU-020 - Gerar QR Code de Cupom

ID: CU-020

Nome: Gerar QR Code de Cupom

Ator Principal: Administrador, Parceiro Comercial, Editor, Agência, Agente

Pré-condições: Usuário autenticado; cupom existente na atração

Pós-condições: QR Code do cupom exibido e disponível para download/compartilhamento

Requisitos Relacionados: RF-018, WF-022

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Gestão de Cupons e seleciona um cupom.
2. O ator clica em Gerar QR Code.
3. O sistema exibe o modal com o QR Code do cupom e opção de download/compartilhar.
4. O ator utiliza o QR Code ou link conforme necessidade.

### 5.21 CU-021 - Visualizar Gráficos e Analytics

ID: CU-021

Nome: Visualizar Gráficos e Analytics

Ator Principal: Administrador, Parceiro Comercial

Atores Secundários: Sistema (Google Analytics)

Pré-condições: Usuário autenticado; atração selecionada; integração Google Analytics configurada

Pós-condições: Dashboard com gráficos e KPIs do Google Analytics exibido

Requisitos Relacionados: RF-019, WF-025

Fluxo Principal:

O ator acessa Detalhes da Atração &gt; Gráficos Analytics.

O sistema verifica se há integração Google Analytics para a atração.

Se houver, o sistema exibe cards de KPIs e gráficos.

Se não houver, o sistema exibe mensagem solicitando integração.

### 5.22 CU-022 - Gerenciar Usuários da Atração

ID: CU-022

Nome: Gerenciar Usuários da Atração

Ator Principal: Administrador, Parceiro Comercial

Pré-condições: Usuário autenticado; atração selecionada

Pós-condições: Usuários vinculados à atração (Editor, Leitor, Agência, Agente) cadastrados/editados/desvinculados

Requisitos Relacionados: RF-021, WF-026, WF-027

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Usuários.
2. O sistema exibe a lista de usuários vinculados à atração.
3. O ator pode adicionar usuário (vincular existente ou criar Editor/Leitor no contexto da atração), editar ou desvincular.
4. O sistema valida (não permite vincular Parceiro Comercial nem Turista) e salva.
5. O sistema atualiza a lista.

Fluxos de Exceção:

4a. Tentativa de vincular perfil não permitido: Sistema exibe mensagem e impede.

### 5.23 CU-023 - Visualizar Negociação Financeira

ID: CU-023

Nome: Visualizar Negociação Financeira

Ator Principal: Administrador, Parceiro Comercial

Pré-condições: Usuário autenticado; atração selecionada; acesso ao submódulo Gestão Financeira

Pós-condições: Telas de Condições Comerciais e Informações Financeiras visualizadas

Requisitos Relacionados: RF-023, WF-028, WF-029

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Gestão Financeira &gt; Negociação Financeira.
2. O sistema exibe submenus: Condições Comerciais e Informações Financeiras.
3. O ator acessa Condições Comerciais e visualiza (e edita se Admin) as condições vinculadas ao contrato da atração.
4. O ator acessa Informações Financeiras e visualiza (e edita se Admin) dados financeiros vinculados.

### 5.24 CU-024 - Visualizar Resumo das Despesas

ID: CU-025

Nome: Visualizar Resumo das Despesas

Ator Principal: Administrador, Parceiro Comercial

Pré-condições: Usuário autenticado; atração(s) com dados financeiros

Pós-condições: Tela Resumo das Despesas exibida com tabela principal e detalhes expansíveis

Requisitos Relacionados: RF-024, WF-030

Fluxo Principal:

1. O ator acessa Detalhes da Atração (ou Gestão Financeira) &gt; Resumo das Despesas.
2. O sistema exibe a tabela principal com atrações agrupadas por data de liberação.
3. O ator pode expandir uma linha para ver a tabela detalhada.
4. O ator pode solicitar repasse (Parceiro) ou autorizar/registrar repasse (Admin) conforme CU-027 e CU-028.

### 5.25 CU-025 - Solicitar Repasse

ID: CU-025

Nome: Solicitar Repasse

Ator Principal: Parceiro Comercial

Pré-condições: Usuário autenticado como Parceiro Comercial; valor disponível para repasse; prazo de pagamento respeitado

Pós-condições: Solicitação de repasse registrada com duas despesas em status Pendente

Requisitos Relacionados: RF-024

Fluxo Principal:

1. O ator acessa Resumo das Despesas e seleciona a atração.
2. O ator clica em Solicitar Repasse.
3. O sistema exibe o modal com valor disponível para repasse.
4. O ator pode clicar em Valor Total para preencher o valor máximo ou informar valor menor.
5. O ator confirma a solicitação.
6. status Pendente.
7. O sistema atualiza a tabela detalhada e exibe confirmação.

Fluxos de Exceção:

6a. Valor maior que disponível: Sistema exibe erro e impede confirmação.

6b. Prazo de pagamento não respeitado: Sistema impede ou exibe mensagem com prazo restante.

### 5.26 CU-026 - Autorizar/Registrar Repasse

ID: CU-026

Ator Principal: Administrador

Pré-condições: Usuário autenticado como Administrador; despesa de repasse com status Pendente

Pós-condições: Status da despesa alterado para Autorizado

Requisitos Relacionados: RF-024

Fluxo Principal:

1. O ator acessa Resumo das Despesas (ou lista de despesas pendentes).
2. O sistema exibe as despesas com status Pendente.
3. O ator altera o status da despesa de repasse de Pendente para Autorizado (e registra pagamento se aplicável).
4. O sistema atualiza o status na tabela detalhada e exibe confirmação.

### 5.27 CU-027 - Validar Ingresso (Leitura QR Code)

ID: CU-027

Nome: Validar Ingresso (Leitura QR Code)

Ator Principal: Leitor, Administrador, Parceiro Comercial

Atores Secundários: Sistema (câmera, validação)

Pré-condições: Usuário autenticado; vinculado à atração; permissão de câmera concedida

Pós-condições: Ingresso marcado como validado no sistema; registro de data/hora e usuário que validou; tabela de histórico atualizada

Requisitos Relacionados: RF-018, RF-025

Fluxo Principal:

1. O ator acessa Detalhes da Atração &gt; Validar Ingressos.
2. O ator clica em Iniciar Validação.
3. O sistema solicita permissão de acesso à câmera; o ator concede.
4. O sistema exibe a visualização da câmera em tempo real.
5. O ator posiciona o QR Code do ingresso no campo de leitura.
6. O sistema processa o QR Code, valida se o ingresso é da atração atual, não está cancelado e não foi validado anteriormente.
7. O sistema marca o ingresso como Validado, registra data/hora e usuário, atualiza a tabela de histórico e exibe mensagem de sucesso.

Fluxos de Exceção:

6a. QR Code inválido ou ingresso já utilizado: Sistema exibe mensagem de erro e não altera status.

6b. Ingresso cancelado: Sistema exibe mensagem "Ingresso cancelado. Entrada bloqueada."

6c. Erro de leitura do QR Code: Sistema exibe "Erro na leitura do QR Code. Tente novamente."

3a. Permissão de câmera negada: Sistema exibe mensagem informativa.

### 5.28 CU-028 - Realizar Checklist de Visita

ID: CU-028

Nome: Realizar Checklist de Visita

Ator Principal: Editor, Leitor

Pré-condições: Usuário autenticado com perfil Editor ou Leitor; vinculado à atração

Pós-condições: Checklist de visita enviado e registrado no sistema

Requisitos Relacionados: RF-014

Fluxo Principal:

1. O ator acessa a funcionalidade de Checklist de Visita.
2. O sistema exibe o formulário de checklist (itens a preencher durante a visita).
3. O ator preenche os itens e envia.
4. O sistema valida e salva o checklist.
5. O sistema exibe confirmação de envio.

### 5.29 CU-029 - Gerenciar Imagens da Atração

ID: CU-029

Nome: Gerenciar Imagens da Atração

Ator Principal: Administrador, Parceiro Comercial, Editor

Pré-condições: Usuário autenticado com permissão; atração selecionada

Pós-condições: Imagens da atração (foto de capa, materiais home, etc.) atualizadas

Requisitos Relacionados: RF-006, RF-014

Fluxo Principal:

1. O ator acessa Detalhes da Atração e entra na edição da atração.
2. O sistema exibe a etapa de Foto de Capa e Materiais (Home, Imagem da atração, Fundo).
3. O ator faz upload, substitui ou remove imagens.
4. O sistema valida (tamanho, formato conforme RNF) e salva.
5. O sistema exibe confirmação e atualiza a exibição.

## 6 Anexos

Lista de Wireframes

1. WF-001 - Tela de login.png
2. WF-002 - Dashboard.png
3. WF-003 - Detalhes da Atração/Totais da atração.png
4. WF-004 - Perfil.png
5. WF-005 - Gestão de Usuários.png
6. WF-006 - Adicionar Usuários.png
7. WF-007 - Gestão de Contratos.png
8. WF-008 - Gestão de contratos/adicionar contrato.png
9. WF-009 - Configurações Comerciais.png
10. WF-010 - Configurações Comerciais/condição comercial.png
11. WF-011 - Configurações Comerciais/informação financeira.png
12. WF-012 - Gestão de Atrações.png
13. WF-013 - Gestão de atrações/Adicionar Atração 1.png
14. WF-014 - Gestão de atrações/Adicionar Atração 2.png
15. WF-015 - Gestão de atrações/Adicionar Atração 3.png
16. WF-016 - Detalhes da Atração/Categorias.png
17. WF-017 - Detalhes das Atrações/Pesquisar Ingresso – Administrador.png
18. WF-018 - Detalhes da Atração/Pesquisar Ingresso/Detalhe do Ingresso.png
19. WF-019 - Detalhes da Atração/Gestão de ingresso.png
20. WF-020 - Detalhes da Atração/Gestão de Ingresso/Adicionar Ingresso.png
21. WF-021 - Detalhes da Atração/Gestão de Cupons.png
22. WF-022 - Detalhes da Atração/Gestão de Cupons/Gerar QR Code.png
23. WF-023 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom.png
24. WF-024 - Detalhes da Atração/Gestão de Cupons/Adicionar Cupom Agencia.png
25. WF-025 - Detalhes da Atração/Graficos Analytics.png
26. WF-026 - Detalhes da Atração/Usuários.png
27. WF-027 - Detalhes da Atração/Gestão de usuários/Adicionar usuário.png
28. WF-028 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Condições Comerciais.png
29. WF-029 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Informações Financeiras.png
30. WF-030 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Resumo das Despesas.png
31. WF-031 - Detalhes da Atração/Gestão financeira/Negociação Financeira/Validar Ingressos.png
32. WF-032 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Vendas.png
33. WF-033 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Vendas.png
34. WF-034 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Abandono de Carrinho.png
35. WF-035 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Abandono de Carrinho.png
36. WF-036 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Ingresso Detalhado.png
37. WF-037 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Ingresso Detalhado.png
38. WF-038 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Categorias.png
39. WF-039 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Categorias.png
40. WF-040 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Cortesias Emitidas.png
41. WF-041 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Cortesias Emitidas.png
42. WF-042 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Validações.png
43. WF-043 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Validações.png
44. WF-044 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Comissões.png
45. WF-045 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Comissões.png
46. WF-046 - Detalhes da Atração/Gestão financeira/Relatórios da atração/Borderô Resumido.png
47. WF-047 - PDF Detalhes da Atração/Gestão financeira/Relatórios da atração/Borderô Resumido.png

## 7 Entregas do Projeto

A tabela abaixo apresenta os principais marcos de entrega do projeto Curitiba 360:

| Tipo de entrega            | Descrição                                                                                                                       | Data / Prazo para Entrega   |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Levantamento de Requisitos | Análise e documentação completa dos requisitos funcionais, não funcionais e regras de negócio do sistema Curitiba 360.          | 05/02/2026                  |
| Prototipação (Wireframes)  | Criação dos wireframes e protótipos de todas as telas do sistema para validação com o cliente.                                  | 05/02/2026                  |
| Desenvolvimento            | Implementação completa das funcionalidades do sistema conforme requisitos especificados, incluindo módulo web e administrativo. |                             |
| Testes                     | Execução de testes unitários, de integração e de sistema para garantir a qualidade das funcionalidades desenvolvidas.           |                             |
| Homologação                | Entrega do sistema em ambiente de homologação para validação e aceite do cliente.                                               |                             |
| Implantação                | Deploy do sistema em ambiente de produção, configuração de infraestrutura e migração de dados.                                  |                             |
| Treinamento                | Capacitação dos usuários finais e administradores do sistema para operação adequada da plataforma.                              |                             |

## 8 Assinaturas

ASSINATURA DO GERENTE DO CLIENTE						ASSINATURA USUÁRIO

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_										 \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_