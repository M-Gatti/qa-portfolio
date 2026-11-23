# Relatório de resumo de teste

📚 **Referência de estudo** · Baseado no relatório de conclusão de teste do syllabus CTFL v4.0 (5.3.2) e na ISO/IEC/IEEE 29119-3. Na prática eu reporto resultados de teste ao time; este formato completo de relatório é referência de estudo. Exemplo fictício.
[English](../en/test-summary-report.md)

O relatório existe para apoiar **uma decisão**: isso pode ir para produção, e com quais riscos? Comece pela resposta, depois as evidências.

---

## Template
**1. Recomendação** · Go / Go com riscos / No-go, em uma ou duas frases.

**2. Escopo** · O que foi testado (histórias, jornadas, plataformas, build) e o que não foi.

**3. Resultados**
| Métrica | Valor |
|---|---|
| Casos planejados / executados | |
| Passaram / falharam / bloqueados / não executados | |
| Critérios de aceite cobertos | (da [matriz de rastreabilidade](matriz-de-rastreabilidade.md)) |

**4. Defeitos**
| Severidade | Encontrados | Corrigidos | Abertos | Aceitos pelo PO |
|---|---|---|---|---|

**5. Riscos abertos** · Cada defeito aberto ou área não testada, o impacto e quem aceitou.

**6. Desvios do plano** · O que mudou e por quê (escopo, ambiente, datas).

**7. Lições** · Uma ou duas coisas para manter ou mudar no próximo ciclo.

---

## Exemplo (fictício: TrilhaFit, release 2.3)
**1. Recomendação:** **Go com riscos.** Reserva e lista de espera estão estáveis em todas as plataformas. Um defeito Alto em notificações segue aberto, aceito pelo PO com contorno.

**2. Escopo:** histórias BK-101 a BK-118, build 2.3.0 (418), web, Android 13 e 14, iOS 16 e 17. Não testado: pagamentos (outro time), layout de tablet.

**3. Resultados**
| Métrica | Valor |
|---|---|
| Casos planejados / executados | 142 / 138 |
| Passaram / falharam / bloqueados / não executados | 131 / 4 / 3 / 4 |
| Critérios de aceite cobertos | 39 de 41 |

**4. Defeitos**
| Severidade | Encontrados | Corrigidos | Abertos | Aceitos pelo PO |
|---|---|---|---|---|
| Crítica | 1 | 1 | 0 | |
| Alta | 4 | 3 | 1 | 1 (BUG-129) |
| Média | 7 | 5 | 2 | 2 |
| Baixa | 5 | 2 | 3 | 3 |

**5. Riscos abertos:** BUG-129: alunos promovidos da lista de espera a menos de 2 h da aula não recebem push. Impacto: podem perder a aula. Contorno: o e-mail é enviado. Aceito pelo PO até a 2.3.1.

**6. Desvios:** o critério de saída "nenhum defeito Alto aberto" do [plano de teste](plano-de-teste.md) não foi atendido; o PO aceitou o BUG-129 por escrito como exceção. 3 casos bloqueados por queda de staging no dia 8; executados de novo no dia 9. Layout de tablet movido para a 2.4.

**7. Lições:** as regras da lista de espera geraram a maior parte das dúvidas; na próxima, montar a tabela de decisão no refinamento.
