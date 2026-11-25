# Template de história de usuário (PBI)

✅ **Aplicado na prática** na revisão de histórias antes de testar (o checklist abaixo).
📚 **Referência de estudo** na escrita de histórias do zero: normalmente é trabalho do PO; o formato segue a prática ágil comum e o syllabus CTFL v4.0 (4.5, abordagens de teste baseadas em colaboração).
[English](../en/user-story.md)

---

## Template
```markdown
# [ID] <título curto: quem + o quê>

**Como** <tipo de usuário>
**Quero** <ação>
**Para** <benefício>

## Contexto
Por que agora, link do protótipo, histórias relacionadas.

## Regras de negócio
- R1: ...
- R2: ...

## Critérios de aceite
- CA1: Dado <estado>, quando <ação>, então <resultado observável>
- CA2: ...

## Fora do escopo
O que esta história não cobre.

## Plataformas e perfis
Web / Android / iOS · quais perfis de usuário são afetados.

## Dúvidas em aberto
Preenchidas no refinamento; as respostas ficam registradas aqui.
```

## Checklist de revisão do QA (antes de a história ficar "pronta")
- [ ] Todo critério de aceite tem resultado **observável**
- [ ] As regras têm **limites e exceções** escritos (mínimo, máximo, o que acontece na borda)
- [ ] **Caminhos negativos** descritos (erros, telas vazias, sem permissão)
- [ ] Protótipo e texto **concordam**
- [ ] **Perfis e plataformas** explícitos
- [ ] Dependências (outras histórias, APIs, dados) listadas
- [ ] Pequena o suficiente para testar dentro da sprint

---

## Exemplo (fictício: TrilhaFit)
**[BK-104] Aluno reserva vagas numa aula**

**Como** aluno **quero** reservar de 1 a 4 vagas numa aula **para** treinar com convidados.

**Regras de negócio**
- R1: de 1 a 4 vagas por reserva.
- R2: a reserva não pode passar das vagas restantes da aula.
- R3: alunos Basic podem ter no máximo 2 reservas ativas.

**Critérios de aceite**
- CA1: Dado uma aula com vagas, quando o aluno reserva de 1 a 4 vagas, então a reserva aparece em *Minhas aulas* como *Confirmada*.
- CA2: Dado que a aula atinge a capacidade, então os outros alunos veem "Lotada" e *Entrar na lista de espera*.
- CA3: Dado um aluno Basic com 2 reservas ativas, quando tenta reservar de novo, então o app mostra "Seu plano permite 2 reservas ativas".

**Fora do escopo:** pagamento de convidados. **Plataformas:** web, Android, iOS. **Perfis:** aluno (Basic, Plus, Premium).
