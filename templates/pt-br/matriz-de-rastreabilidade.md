# Matriz de rastreabilidade de requisitos

📚 **Referência de estudo** · Ligar cada caso à sua história faz parte da minha prática; este formato completo de matriz (requisito ↔ casos ↔ resultados ↔ defeitos) foi montado a partir do syllabus CTFL v4.0 (1.4.4, rastreabilidade) e da prática comum do mercado. Exemplo fictício.
[English](../en/traceability-matrix.md)

Uma matriz de rastreabilidade responde três perguntas de relance:
1. **Todo requisito está testado?** (linha sem caso é lacuna)
2. **O que esta falha afeta?** (do defeito de volta ao requisito)
3. **O que eu rodo de novo se isto mudar?** (do requisito para os casos)

---

## Template
| Requisito / critério | Descrição | Risco | Casos de teste | Último resultado | Defeitos | Cobertura |
|---|---|---|---|---|---|---|
| *ID* | *texto curto* | *A/M/B* | *IDs dos casos* | *Pass / Fail / Blocked / Não executado* | *IDs dos bugs* | *Coberto / Parcial / Não coberto* |

### Regras
- Uma linha por **critério de aceite ou regra**, não por história: uma história com cinco critérios tem cinco linhas.
- A linha só fica **Coberta** se todos os casos rodaram e passaram; **Parcial** se só parte rodou ou algum falhou.
- Mantenha na ferramenta de gestão de testes quando der; planilha fica desatualizada rápido.

---

## Exemplo (fictício: TrilhaFit, release 2.3)
| Requisito | Descrição | Risco | Casos de teste | Último resultado | Defeitos | Cobertura |
|---|---|---|---|---|---|---|
| BK-104 CA1 | Reservar de 1 a 4 vagas | A | TC-0101 a TC-0106 | Pass | | Coberto |
| BK-104 CA2 | Aula aparece "Lotada" na capacidade | A | TC-0107, TC-0108 | Pass | | Coberto |
| BK-108 R1 | Crédito no cancelamento (4 regras) | A | TC-0150 a TC-0153 | Fail | BUG-140 | Parcial |
| BK-111 CA2 | Promoção automática da lista de espera | A | TC-0230, TC-0232 | Pass | | Coberto |
| BK-111 CA3 | Notificação na promoção | M | TC-0231 | Fail | BUG-129 | Parcial |
| BK-115 CA1 | Instrutor vê só as próprias aulas | A | | Não executado | | **Não coberto** |

**Leitura:** a BK-115 ainda não tem casos e é de risco alto, então é a primeira coisa a resolver. BK-108 e BK-111 têm defeitos abertos que, pelos critérios de saída, seguram o release.

## Linha de resumo para o relatório de teste
*6 critérios · 3 cobertos · 2 parciais (2 defeitos abertos) · 1 não coberto.*
