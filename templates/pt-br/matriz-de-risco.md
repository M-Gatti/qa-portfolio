# Matriz de risco (teste baseado em risco)

📚 **Referência de estudo** · Baseada no CTFL v4.0, seção 5.2 (gestão de risco). Exemplo fictício.
[English](../en/risk-matrix.md)

Teste baseado em risco gasta o esforço de teste onde a falha doeria mais. **Nível de risco = probabilidade × impacto.**

---

## Escalas
| Nota | Probabilidade | Impacto |
|---|---|---|
| 1 | Improvável: código simples, estável, conhecido | Pequeno: cosmético, contorno fácil |
| 2 | Possível: código novo ou de complexidade moderada | Moderado: funcionalidade prejudicada, existe contorno |
| 3 | Provável: complexo, muda muito, integrações, histórico de bugs | Grave: fluxo principal travado; dinheiro, dados ou confiança em jogo |

## Matriz
| | Impacto 1 | Impacto 2 | Impacto 3 |
|---|---|---|---|
| **Probabilidade 3** | 3 · Médio | 6 · Alto | 9 · Alto |
| **Probabilidade 2** | 2 · Baixo | 4 · Médio | 6 · Alto |
| **Probabilidade 1** | 1 · Baixo | 2 · Baixo | 3 · Médio |

## O que o nível muda
| Nível | Resposta de teste |
|---|---|
| Alto (6 a 9) | Várias técnicas, casos negativos, todas as plataformas, sessão exploratória, cedo na sprint, entra na regressão |
| Médio (3 a 4) | Técnicas principais, plataformas principais, entra na regressão se a área muda muito |
| Baixo (1 a 2) | Caminho feliz e smoke |

## Registro
| ID | Risco (o que pode dar errado) | P | I | Nível | Resposta | Responsável | Situação |
|---|---|---|---|---|---|---|---|

---

## Exemplo (fictício: TrilhaFit, release 2.3)
| ID | Risco | P | I | Nível | Resposta |
|---|---|---|---|---|---|
| R1 | Dois alunos pegam a última vaga ao mesmo tempo | 2 | 3 | 6 · Alto | Testes de concorrência na API de reserva; sessão exploratória; entra na regressão |
| R2 | Regra de crédito aplicada errado no cancelamento | 2 | 3 | 6 · Alto | Tabela de decisão, as 4 regras testadas em todas as plataformas |
| R3 | Notificação da lista de espera não enviada | 3 | 2 | 6 · Alto | Casos de transição de estado; conferir push no Android e no iOS |
| R4 | Ordenação da lista de aulas errada em tela pequena | 2 | 1 | 2 · Baixo | Smoke em um aparelho pequeno |

Revise o registro quando o escopo mudar ou um risco se concretizar. Risco que continua gerando bug sobe de probabilidade.
