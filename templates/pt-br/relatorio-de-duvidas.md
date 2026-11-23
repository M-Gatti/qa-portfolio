# Relatório de dúvidas de PBI

✅ **Aplicado na prática** · O formato que uso para mandar as dúvidas de QA sobre uma história para produto, negócio e devs antes de testar. Exemplo fictício.
[English](../en/story-clarification-report.md)

**Por quê:** regra ambígua é o bug mais barato de corrigir, porque se corrige numa frase, não no código. E uma mensagem organizada respeita mais o tempo das pessoas do que dez perguntas soltas.

---

## Formato
> **[ID da história] Título da história**
> Oi, pessoal! Revisando esta história para teste, encontrei alguns pontos que gostaria de confirmar. Podem responder direto embaixo de cada item.
>
> **<Referência da regra ou do critério de aceite>**
> **Observação:** o que a história diz (citado ou resumido) e o que falta ou conflita.
> **Dúvida:** uma pergunta direta, que dá para responder em poucas palavras. Quando der, ofereça opções.

### Regras
1. **Agrupe por regra ou critério**, na ordem da história.
2. **Uma dúvida por item.** Duas perguntas viram dois itens.
3. **Cite a fonte** (critério, regra, tela do protótipo), para ninguém precisar procurar.
4. **Ofereça opções** quando puder: "A ou B?" é respondido mais rápido que "como deveria funcionar?".
5. **Sem opinião sobre a solução.** O objetivo é confirmar o comportamento, não redesenhar.
6. **Registre as respostas** na história, para que virem parte da base de teste.

---

## Exemplo (fictício: TrilhaFit)
> **[BK-111] Promoção da lista de espera**
> Oi, pessoal! Revisando esta história para teste, encontrei alguns pontos que gostaria de confirmar.
>
> **CA 2: "Quando abre uma vaga, o primeiro aluno da lista de espera é reservado automaticamente."**
> **Observação:** a história não diz o que acontece se o primeiro aluno já atingiu o limite de reservas do plano.
> **Dúvida:** nesse caso, a vaga vai para o próximo da lista, ou o primeiro mantém a posição?
>
> **CA 3: "O aluno recebe uma notificação."**
> **Observação:** o protótipo mostra uma notificação push; o texto não fala de e-mail.
> **Dúvida:** só push, ou push e e-mail?
>
> **Regra R4: cancelamento tardio (menos de 12 h)**
> **Observação:** uma promoção pode acontecer a menos de 12 h da aula.
> **Dúvida:** se um aluno promovido em cima da hora cancelar, a regra de cancelamento tardio vale para ele?
