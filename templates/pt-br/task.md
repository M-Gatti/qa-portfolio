# Template de task de QA

✅ **Aplicado na prática** · Como registro o trabalho de QA no board (Jira, Azure DevOps): design de teste, execução, massa de teste, documentação. Exemplo fictício.
[English](../en/task.md)

A task deixa o trabalho de QA **visível no board**. Se testar uma história leva um dia, o board precisa mostrar isso.

---

## Template
| Campo | O que vai |
|---|---|
| **Título** | `[QA] Verbo + objeto + história`, ex.: "[QA] Testar promoção da lista de espera da BK-111" |
| **Pai** | A história a que pertence |
| **Tipo de trabalho** | Design de teste · Execução · Reteste · Massa de teste · Documentação · Regressão |
| **Descrição** | O que será feito, em 2 ou 3 linhas |
| **Pronto quando** | Saída concreta: casos escritos e ligados, executados em todas as plataformas, resultados e evidências anexados |
| **Plataformas** | Web / Android / iOS |
| **Estimativa** | Horas ou pontos, conforme o combinado do time |
| **Impedimentos** | Se bloqueada: motivo e responsável (veja [Fail × Blocked](../../flows/pt-br/fail-vs-blocked.md)) |

---

## Exemplo (fictício: TrilhaFit)
| Campo | Valor |
|---|---|
| Título | [QA] Testar promoção da lista de espera da BK-111 |
| Pai | BK-111 |
| Tipo de trabalho | Design de teste + execução |
| Descrição | Escrever casos para CA1 a CA4 (transição de estado + tabela de decisão do cancelamento tardio) e executar em web, Android e iOS |
| Pronto quando | Casos ligados à BK-111 no repositório de testes; todos executados; bugs abertos com gravação; dúvidas enviadas ao PO |
| Plataformas | Web, Android, iOS |
| Estimativa | 6 h |
| Impedimentos | Nenhum |
