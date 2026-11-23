# Checklist de massa de teste e privacidade (LGPD)

📚 **Referência de estudo** · Montado a partir do estudo da Lei Geral de Proteção de Dados (LGPD, Lei 13.709/2018), aplicada à rotina de QA. É um apoio para testar, **não é orientação jurídica**; a palavra final é do encarregado (DPO) e do jurídico da empresa.
[English](../en/test-data-privacy-checklist.md)

Dois lados da privacidade para o QA:
1. **Como eu trato dados enquanto testo** (massa, evidências, bug reports).
2. **O que eu testo no produto** (funcionalidades que existem por causa da lei).

---

## Parte 1: Tratando dados enquanto testo
**Massa de teste**
- [ ] Preferir **dados sintéticos** (nomes inventados, documentos gerados em formato válido, e-mails `@example.com`)
- [ ] Dado de produção em ambiente de teste só **anonimizado** e com motivo registrado. Pelo art. 12 da LGPD, dado anonimizado não é dado pessoal, salvo se a anonimização puder ser revertida com esforço razoável
- [ ] Só os campos que o teste precisa (princípio da **necessidade**, art. 6º, III)
- [ ] Contas de teste são do time, não de pessoas reais; nenhuma conta pessoal usada para testar
- [ ] Massa removida ou reiniciada quando o ciclo de teste termina

**Evidências e registros**
- [ ] Prints e gravações mostram só contas de teste; o que for real é borrado antes de anexar
- [ ] Nada de senha, token ou número completo de documento em bug report, comentário ou chat
- [ ] Evidência guardada na ferramenta do time (board, gestão de testes), não em aparelho ou nuvem pessoal
- [ ] Logs e respostas de API anexados só com os campos pessoais mascarados

## Parte 2: O que testar no produto
| Área | Ideias de teste | Referência na LGPD |
|---|---|---|
| Consentimento | Consentimento opcional onde deve ser; dá para revogar tão fácil quanto dar; o produto respeita a revogação | Art. 8º |
| Direitos do titular | Usuário consegue ver, corrigir, exportar e pedir exclusão dos dados; a exclusão remove ou anonimiza de verdade | Art. 18 |
| Controle de acesso | Cada perfil vê só o que precisa; URL direta ou chamada de API não contornam permissão | Art. 6º, VII, e art. 46 |
| Dado sensível | Dado de saúde, biométrico e semelhantes tem acesso mais restrito e não aparece onde não precisa | Art. 5º, II, e art. 11 |
| Transparência | Aviso de privacidade fácil de achar e coerente com o que o produto realmente coleta | Art. 6º, VI, e art. 9º |
| Minimização | Formulário pede só o que a funcionalidade usa; campo opcional é opcional de verdade | Art. 6º, III |
| Retenção | Dado removido ou anonimizado quando a finalidade informada termina | Arts. 15 e 16 |

## Exemplo (fictício: TrilhaFit)
- **Massa:** alunos *ana.basic*, *bruno.plus*, *carla.premium*, e-mails `@example.com`, CPFs de gerador, nenhuma foto real.
- **Caso de teste:** *[Privacidade] Aluno pede exclusão da conta: dados pessoais removidos, histórico de reservas mantido só como estatística anonimizada.*
- **Teste de acesso:** um instrutor abre `/members/{id}` de um aluno que não é da turma dele → acesso negado (403), nenhum dado na resposta.
