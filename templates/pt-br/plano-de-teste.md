# Template de plano de teste

📚 **Referência de estudo** · Estrutura baseada no syllabus CTFL v4.0 (seção 5.1.1, conteúdo do plano de teste) e no documento de plano de teste da ISO/IEC/IEEE 29119-3.
[English](../en/test-plan.md)

Um plano de teste responde a uma pergunta: *como vamos dar ao time informação suficiente para decidir se isso pode ir para produção?*
Mantenha curto. Um plano que ninguém lê é pior que uma página que todo mundo segue.

> Os valores de exemplo em *itálico* usam o **TrilhaFit**, um app fictício de reserva de aulas de academia.

---

## 1. Contexto
| Campo | Preencher |
|---|---|
| Produto / funcionalidade | *TrilhaFit: reserva de aulas e lista de espera (release 2.3)* |
| Versão deste plano | *1.0, 23/11/2026* |
| Responsável | *Nome do QA* |
| Base de teste | *Histórias BK-101 a BK-118, protótipo v4, regras de reserva v2* |
| Plataformas | *Web (Chrome, Safari), Android 13+, iOS 16+* |

## 2. Escopo
**Dentro:** *reservar, cancelar, promoção da lista de espera, limite de reservas por plano.*
**Fora:** *pagamentos (cobertos pelo time de pagamentos), painel administrativo.*

## 3. Objetivos
O que o teste precisa mostrar. Escreva de um jeito que dê para dizer "cumprido" ou "não cumprido".
- *Todo critério de aceite de BK-101 a BK-118 tem ao menos um teste executado.*
- *Nenhum defeito Crítico ou Alto aberto no release.*

## 4. Premissas e restrições
- *Staging tem as mesmas regras de reserva que produção.*
- *Só um iPhone físico disponível; outras versões em dispositivos na nuvem.*

## 5. Partes interessadas e comunicação
| Quem | Precisa de | Canal / frequência |
|---|---|---|
| *PO* | *Prontidão para o release* | *Relatório de teste no fim de cada sprint* |
| *Devs* | *Defeitos com evidência* | *Board, assim que encontrados* |

## 6. Riscos
Riscos de produto definem *o que* testar com mais profundidade; riscos de projeto ameaçam *o próprio plano*. Dê nota a cada um (probabilidade × impacto, de 1 a 3).

| ID | Risco | Tipo | P | I | Nota | Resposta |
|---|---|---|---|---|---|---|
| R1 | *Dois usuários pegam a última vaga ao mesmo tempo* | Produto | 2 | 3 | 6 | *Testes de concorrência na reserva; sessão exploratória* |
| R2 | *Protótipo muda depois do design dos testes* | Projeto | 2 | 2 | 4 | *Revisar os casos no meio da sprint* |

## 7. Abordagem de teste
| Item | Decisão |
|---|---|
| Níveis de teste | *Teste de sistema e teste de aceite (com o PO)* |
| Tipos de teste | *Funcional, regressão dos fluxos de reserva, usabilidade básica, checagens de API nos endpoints de reserva* |
| Técnicas | *Partição de equivalência e valor limite para limites, tabela de decisão para regras de cancelamento, transição de estado para o status da reserva, sessões exploratórias na lista de espera* |
| Massa de teste | *Uma conta de teste por plano (Basic, Plus, Premium) e por papel (aluno, instrutor)* |
| Ambiente | *Staging, dispositivos reais e na nuvem* |
| Independência | *Testado pelo QA, não pelo dev da história* |

## 8. Critérios de entrada e saída
**Entrada (pronto para testar):** *história com critérios de aceite, build em staging, massa de teste disponível.*
**Saída (teste concluído):** *todos os testes planejados executados, nenhum defeito Crítico/Alto aberto, defeitos Médios aceitos pelo PO por escrito.*

## 9. Entregáveis
*Casos de teste na ferramenta de gestão de testes, bug reports, relatório de resumo de teste.*

## 10. Métricas
*Testes executados × planejados, defeitos por severidade e status, critérios de aceite cobertos.*

## 11. Cronograma
| Atividade | Quando |
|---|---|
| *Análise e design de teste* | *Dias 1 a 3 da sprint* |
| *Execução e reteste* | *Conforme as histórias chegam em "Pronto para QA"* |
| *Regressão e resumo* | *Últimos 2 dias da sprint* |

---

### Observações
- O syllabus trata o plano como documento vivo: atualize quando escopo ou risco mudarem e registre o que mudou.
- Em time pequeno, as seções 5, 9 e 10 podem ter uma linha cada.
