# Charter de teste exploratório

📚 **Referência de estudo** · O teste exploratório em si faz parte da minha prática; este formato baseado em sessão (charter, tempo definido, debriefing) é o que estou adotando a partir do syllabus CTFL v4.0 (4.4.2). Exemplo fictício.
[English](../en/exploratory-charter.md)

---

## Template
| Campo | Preencher |
|---|---|
| **Charter** | Explorar *<alvo>* com *<recursos / condições>* para descobrir *<tipo de informação>* |
| **Testador / data** | |
| **Tempo** | 45, 60 ou 90 minutos |
| **Build / ambiente / plataforma** | |
| **Preparação** | Contas, dados e aparelhos necessários |
| **Áreas** | O que entra e o que fica fora desta sessão |
| **Anotações** | Registro corrido: o que tentei, o que vi (com horário, se der) |
| **Bugs** | IDs dos bugs abertos |
| **Dúvidas** | O que perguntar ao PO ou aos devs |
| **Ideias** | Novos casos roteirizados ou novos charters |
| **Divisão do tempo** | % testando / % investigando bug / % preparando |

## Debriefing (5 a 10 minutos)
1. O que cobri? O que ficou de fora?
2. O que encontrei (bugs, dúvidas)?
3. A área é arriscada o suficiente para outra sessão?

---

## Exemplo (fictício: TrilhaFit)
| Campo | Valor |
|---|---|
| Charter | Explorar **reservas com convidados** com **troca de plano no meio do fluxo** para descobrir **inconsistências de limite e de crédito** |
| Tempo | 60 min |
| Build / ambiente | 2.3.0 (412), staging, Android 14 e web |
| Preparação | *bruno.plus* com 2 reservas ativas; acesso de admin para trocar plano |
| Anotações | 10:05 Reservei 3 vagas no Plus. 10:12 Baixei para Basic durante a confirmação: a reserva manteve 3 vagas (o limite do Basic não é 2?). 10:20 Mesma coisa na web: bloqueou corretamente. |
| Bugs | BUG-131 (Android mantém o limite do plano antigo durante a confirmação) |
| Dúvidas | O downgrade vale para reservas existentes ou só para novas? |
| Ideias | Caso roteirizado de downgrade durante a confirmação em cada plataforma |
| Divisão do tempo | 60 / 30 / 10 |
