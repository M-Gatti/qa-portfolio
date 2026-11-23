# Template de caso de teste

✅ **Aplicado na prática** · A estrutura e as regras são as que uso para escrever casos numa ferramenta de gestão de testes (Azure Test Plans). O exemplo é fictício.
[English](../en/test-case.md)

---

## Campos
| Campo | O que vai |
|---|---|
| **Título** | `[Área] Ação + condição + resultado esperado`. Dá para entender sem abrir o caso |
| **História / requisito** | ID da história ou regra que ele cobre (rastreabilidade) |
| **Plataforma** | Web, Android, iOS ou todas |
| **Prioridade** | 1 (bloqueia o fluxo principal) a 3 (cosmético ou caminho raro) |
| **Técnica** | Qual técnica gerou o caso (partição, valor limite, tabela de decisão, transição de estado, suposição de erro) |
| **Pré-condições** | Estado que precisa existir antes do passo 1: conta, dados, permissões |
| **Massa de teste** | Valores exatos, não "um usuário válido" |
| **Passos** | Uma ação por passo |
| **Resultado esperado** | Resultado observável por passo: texto, estado, tela, resposta da API |
| **Tags** | Área, tipo (smoke, regressão), risco |

## Regras de escrita
1. **Um comportamento por caso.** Se o título precisa de "e", provavelmente são dois casos.
2. **Resultado esperado observável.** "Funciona corretamente" não é resultado esperado; "A reserva aparece em *Minhas aulas* com status *Confirmada*" é.
3. **Passo é ação, não verificação.** A verificação fica na coluna de resultado esperado.
4. **Massa explícita.** Qualquer pessoa do time precisa conseguir executar sem perguntar.
5. **Um caso, várias plataformas.** Escreva uma vez e marque as plataformas. Separe só quando o comportamento muda de verdade.
6. **Ligue a história.** Caso sem rastreabilidade não mostra cobertura.

---

## Exemplo (fictício: TrilhaFit)

**Título:** [Reserva] Reservar aula com 1 vaga restante: reserva confirmada e aula fica lotada
**História:** BK-104 · **Plataforma:** Web, Android, iOS · **Prioridade:** 1 · **Técnica:** Análise de valor limite
**Pré-condições:** Aluna *ana.basic* (plano Basic, 0 reservas ativas) logada. Aula *Spinning, seg 07:00* com capacidade 20 e 19 reservas.
**Massa:** conta *ana.basic*; aula *CL-0712*

| # | Passo | Resultado esperado |
|---|---|---|
| 1 | Abrir *Aulas* e selecionar *Spinning, seg 07:00* | Detalhe da aula mostra "1 vaga restante" e o botão *Reservar* habilitado |
| 2 | Tocar em *Reservar* | Mensagem "Reserva feita!" é exibida |
| 3 | Abrir *Minhas aulas* | *Spinning, seg 07:00* aparece com status *Confirmada* |
| 4 | Entrar como *bruno.plus* e abrir a mesma aula | Aula mostra "Lotada" e o botão muda para *Entrar na lista de espera* |

**Tags:** reserva, regressão, valor-limite

### Por que este caso existe
O limite da capacidade (19 → 20 reservas) é onde o botão, o contador e a regra da lista de espera mudam ao mesmo tempo. É o lugar mais barato para pegar um erro de "um a mais, um a menos".
