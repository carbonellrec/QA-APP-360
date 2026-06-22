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
