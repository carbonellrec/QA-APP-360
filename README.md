# QA-APP-360 · Verificação de Consistência de Requisitos

Repositório com os relatórios de verificação cruzada de consistência entre Requisitos Funcionais (RF), Regras de Negócio (RN), Casos de Uso (CU) e Critérios de Aceitação (CA) do projeto APP-360.

O objetivo é garantir que a documentação de requisitos esteja alinhada antes da entrega ao cliente e do início dos testes, identificando conflitos entre documentos, lacunas de rastreabilidade e pontos que precisam de decisão de negócio.

## Escopo coberto

| Módulo | Requisitos | Casos de Uso |
|---|---|---|
| Gestão de Agências | RF-044 | CU-030 |
| Cadastro de Agência | RF-045 | CU-031 |
| Gestão de Agentes | RF-046 | CU-032 |
| Operação Comercial – Agência e Agente | RF-047 | CU-033 |
| Comissionamento e Repasse | RF-048 | CU-034 |
| Fila de Reembolsos (Administrador) | RF-049 | CU-035 |
| CMS Institucional | RF-050 | CU-036 |
| CMS Home e Curadoria | RF-051 | CU-037 |
| Tela Inicial por Perfil | RF-056 | CU-039 |
| Parceiros Comerciais | RF-057 | CU-040 |

## Metodologia

Cada relatório cruza o conteúdo de RF, RN, CU e CA relacionados a um mesmo módulo e classifica cada achado em quatro categorias:

- ✓ **Consistente** — o comportamento está descrito de forma coerente entre os documentos.
- ■ **Ponto de atenção** — comportamento não é contraditório, mas está incompleto, ambíguo ou sem CA de cobertura.
- ✗ **Inconsistência** — os documentos descrevem o mesmo comportamento de formas conflitantes.
- 💡 **Sugestão** — melhoria de clareza ou de cobertura de testes, sem impacto funcional imediato.

Os achados são priorizados em **P1 (crítico — corrigir antes da entrega)**, **P2 (importante — próxima revisão)** e **P3 (melhoria — opcional)**.

## Relatórios

| Arquivo | Módulos | Data | ✓ | ■ | ✗ | 💡 |
|---|---|---|---|---|---|---|
| `relatorio-verificacao-rfs-cus.pdf` | RF-044–RF-057 / CU-030–CU-040 (visão geral) | 22/06/2026 | 8 | 11 | 5 | 6 |
| `verificacao-rf044-rf047.pdf` | RF-044 · RF-045 · RF-046 · RF-047 | 27/06/2026 | 8 | 6 | 4 | – |
| `verificacao-rf048-rf049-cu034-cu035.pdf` | RF-048 · RF-049 / CU-034 · CU-035 | 27/06/2026 | 11 | 4 | 2 | 3 |
| `verificacao-rf050-rf051-cu036-cu037.pdf` | RF-050 · RF-051 / CU-036 · CU-037 | 28/06/2026 | 15 | 3 | 1 | 2 |

Os três últimos relatórios são a reverificação, módulo a módulo, dos pontos levantados no relatório geral de 22/06.

## Principais inconsistências críticas (P1)

- **RF-045 vs. RF-044** — status "Ativa" no cadastro manual (RF-045.40) precisava de nota diferenciando esse fluxo do fluxo de aprovação de auto-cadastro (RF-044.26 → "Aguardando Contrato"). Texto de RF-045.40, RN-045.04, CA-045.04 e CA-045.19 estava incompleto/contraditório quanto a "acesso ao backoffice".
- **RF-047.26 → RF-049** — cancelamento parcial pós-24h é encaminhado para a fila de reembolsos, mas o RF-049 foi modelado para pedidos inteiros, sem granularidade por ingresso individual.
- **RF-049.33 → RF-048** — aprovação de reembolso na fila não define o impacto no comissionamento da agência/agente (gap entre os dois módulos).
- **RF-052** — "Lembrete de Visita" classificado como Opt-in com SLA de 15 min pode ser inadequado ao contexto (lembrete sensível a horário); precisa validação com o cliente.
- **RF-056** — Tabela de Menus não lista os módulos disponíveis para o perfil Agente.
- **RF-057 / RF-045** — terminologia divergente ("Substatus da Agência" vs. "Substatus de Operação") entre documentos que descrevem o mesmo conceito.
- **RF-051 / RN-051** — sem SLA definido para expiração do cache de avaliações do Google em caso de falhas consecutivas de sincronização.

A lista completa de achados, com referências exatas a RF/RN/CU/CA e sugestões de correção, está em cada relatório individual.

## Como contribuir / dar sequência

1. Priorizar a resolução dos itens **P1** listados em cada relatório antes da entrega ao cliente.
2. Ao corrigir um requisito, atualizar a referência cruzada correspondente nos demais documentos apontados como inconsistentes.
3. Gerar uma nova rodada de verificação após as correções e versionar o relatório atualizado nesta pasta.

---
*Relatórios gerados a partir de análise cruzada dos documentos de requisitos, casos de uso e critérios de aceitação do projeto APP-360.*
