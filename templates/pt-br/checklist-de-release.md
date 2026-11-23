# Checklist de release

✅ **Aplicado na prática** · Baseado em como participei da coordenação de releases em squads ágeis de SaaS. Versão genérica; adapte ao time.
[English](../en/release-checklist.md)

Ajuste ao tamanho do release: um hotfix pode precisar só da parte de smoke; um release grande precisa de tudo.

---

## Antes do release
**Escopo**
- [ ] Toda história do release está Done, ou foi retirada com acordo do PO
- [ ] Notas do release listam o que sai (histórias, correções, problemas conhecidos)
- [ ] Nenhum bug Crítico/Alto aberto, ou cada um aceito por escrito com o risco

**Regressão**
- [ ] Regressão rodada em staging, priorizada por risco
- [ ] Fluxos principais conferidos em todas as plataformas suportadas: login, fluxo principal, permissões por perfil
- [ ] Áreas tocadas pelo release retestadas

**Aceite**
- [ ] Teste de aceite (UAT) feito com o PO ou o negócio, quando se aplica
- [ ] Limitações conhecidas comunicadas

**Ambiente**
- [ ] Configuração de staging igual à de produção (feature flags, versões)
- [ ] Massa de teste não vai parar em produção

## Go / No-Go
| Condição | ✅ / ❌ |
|---|---|
| Nenhum bug Crítico aberto | |
| Bugs Altos corrigidos ou aceitos com risco documentado | |
| Regressão aprovada | |
| Aceite assinado | |
| Plano de rollback conhecido | |
| Time avisado da janela do release | |

Qualquer ❌ → a decisão vai para o PO e o tech lead, com o risco por escrito.

## Depois do release
**Smoke em produção**
- [ ] App abre e o login funciona em cada plataforma
- [ ] Fluxo principal funciona de ponta a ponta
- [ ] Sem erros críticos no console ou nos logs
- [ ] Permissões se comportam conforme o perfil

**Acompanhamento**
- [ ] Erros e relatos de usuários acompanhados nas primeiras 24 a 48 horas
- [ ] Problema em produção registrado e triado na hora
- [ ] Retro curta: o que escapou e qual teste teria pegado
