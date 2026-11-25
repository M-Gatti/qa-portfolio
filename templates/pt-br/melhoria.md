# Template de melhoria

📚 **Referência de estudo** · Para o que **não é bug** (o produto faz o que foi especificado), mas poderia ser melhor: usabilidade, clareza, acessibilidade, sensação de desempenho. Exemplo fictício.
[English](../en/improvement.md)

**Bug ou melhoria?** Se o comportamento contraria história, regra ou protótipo, é [bug](bug-report.md). Se bate com a especificação mas atrapalha o usuário, é melhoria. Na dúvida, pergunte.

---

## Template
| Campo | O que vai |
|---|---|
| **Título** | `[Área] Situação atual → mudança proposta` |
| **Onde** | Tela, fluxo, plataforma |
| **Comportamento atual** | O que acontece hoje (bate com a especificação) |
| **Problema para o usuário** | Quem é afetado e como; evidência, se houver (gravação, chamados, observação nos testes) |
| **Sugestão** | Uma proposta, não um redesenho. Opções são bem-vindas |
| **Benefício esperado** | O que melhora e como perceberíamos |
| **Esforço estimado** | Pequeno / médio / grande, se souber |
| **Relacionados** | História, tela do protótipo |

O PO decide se e quando. O papel do QA é trazer a observação com evidência.

---

## Exemplo (fictício: TrilhaFit)
**Título:** [Reserva] Limite de vagas só aparece depois do erro → mostrar o limite ao lado do contador

| Campo | Valor |
|---|---|
| Onde | Detalhe da aula, contador de vagas, todas as plataformas |
| Comportamento atual | O aluno consegue subir o contador até 5; ao tocar em *Reservar*, o app mostra "Máximo de 4 vagas por reserva" (bate com a R1 da BK-104) |
| Problema para o usuário | O limite só aparece depois da tentativa. Nas sessões exploratórias, a primeira tentativa com convidados costumava cair nessa mensagem |
| Sugestão | Desabilitar o "+" no 4 e mostrar "Até 4 vagas" embaixo do contador |
| Benefício esperado | Menos tentativas frustradas; mesma regra, mais clara |
| Esforço estimado | Pequeno |
| Relacionados | BK-104, tela "Detalhe da aula" do protótipo v4 |
