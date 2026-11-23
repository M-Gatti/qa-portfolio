# Spec com critérios de aceite

✅ **Aplicado na prática** nos meus próprios projetos: toda automação do meu ambiente pessoal de trabalho com IA começa por uma spec assim. Exemplo fictício.
[English](../en/spec-acceptance-criteria.md)

A spec responde *como é o "pronto"* antes de alguém construir qualquer coisa. Os critérios de aceite são escritos para que cada um **passe ou falhe**, sem espaço para "parece bom".

---

## Template
```markdown
# NNNN: <nome curto>

- Status: rascunho | aprovada | em andamento | entregue | descartada
- Data: AAAA-MM-DD
- Dono: <nome>

## Problema
O que dói hoje, em 2 a 4 linhas. Quem sente e com que frequência.

## Objetivo
O resultado esperado, em uma frase.

## Critérios de aceite
- [ ] <critério verificável>
- [ ] <critério verificável>

## Fora do escopo
O que não será feito agora, para o escopo não crescer no meio do caminho.

## Restrições
Custo, onde roda, dados sensíveis, prazos.

## Como verificar
O teste, comando, amostra real ou checklist que prova cada critério.

## Decisões e histórico
- AAAA-MM-DD: ...
```

## Escrevendo bons critérios
| Fraco | Forte |
|---|---|
| "A lista carrega rápido" | "A lista de aulas mostra as 20 primeiras aulas em menos de 2 s em staging, perfil 4G" |
| "Erros são tratados" | "Se a API de reserva devolver 409, o app mostra 'Essa vaga acabou de ser preenchida' e mantém o aluno na tela da aula" |
| "Funciona no celular" | "Funciona no Android 13+ e no iOS 16+, conferido em pelo menos um aparelho real de cada" |

Para comportamento, **Dado / Quando / Então** mantém o critério testável:
```gherkin
Dado uma aula com 1 vaga restante
Quando um aluno Basic reserva 1 vaga
Então a reserva é confirmada
E a aula aparece como "Lotada" para os outros alunos
```

---

## Exemplo (fictício: TrilhaFit)
**0007: Lembrete semanal de aulas**
- **Objetivo:** alunos com reservas na semana seguinte recebem um e-mail de resumo no domingo.
- **Critérios de aceite**
  - [ ] E-mail enviado no domingo entre 18:00 e 19:00, no fuso do aluno
  - [ ] Só recebe quem tem pelo menos uma reserva *Confirmada* nos próximos 7 dias
  - [ ] Lista aula, dia, horário e local; nenhum outro dado pessoal
  - [ ] Quem recusou e-mails não recebe nada
- **Fora do escopo:** push, SMS.
- **Como verificar:** rodar a rotina em staging com 5 contas de teste cobrindo cada critério; comparar os destinatários com a lista esperada.
