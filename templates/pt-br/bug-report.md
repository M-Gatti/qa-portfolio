# Template de bug report

✅ **Aplicado na prática** · O formato que uso para registrar defeitos em boards do Jira e do Azure DevOps. O exemplo é fictício.
[English](../en/bug-report.md)

Um bom bug report deixa o dev reproduzir o problema **sem precisar falar comigo antes**.

---

## Campos
| Campo | O que vai |
|---|---|
| **Título** | `[Área] O que acontece + quando acontece`. Nada de "não funciona" ou só "erro" |
| **Ambiente** | Ambiente (staging, produção), build/versão, plataforma, aparelho e SO, navegador |
| **Conta / perfil** | Qual conta de teste e perfil (sem senha) |
| **Pré-condições** | Estado necessário antes do passo 1 |
| **Passos para reproduzir** | Numerados, uma ação cada, começando de uma tela conhecida |
| **Resultado esperado** | O que deveria acontecer, com a fonte: história, critério de aceite, regra, protótipo |
| **Resultado obtido** | O que aconteceu, exatamente. Copie mensagens palavra por palavra |
| **Frequência** | Sempre, intermitente (x de y tentativas), uma vez |
| **Severidade** | Impacto no produto (abaixo) |
| **Prioridade** | Urgência para o time. Normalmente definida com o PO, não só pelo QA |
| **Evidência** | Gravação de tela, print, requisição/resposta, logs |
| **Itens relacionados** | História, caso de teste, bugs parecidos |

### Severidade
| Nível | Significado |
|---|---|
| Crítica | Fluxo principal bloqueado, perda de dados ou falha de segurança, sem contorno |
| Alta | Funcionalidade importante quebrada; contorno difícil ou inaceitável para o usuário |
| Média | Funcionalidade parcialmente quebrada; existe contorno razoável |
| Baixa | Cosmético, texto, alinhamento; sem impacto funcional |

**Severidade ≠ prioridade.** Um erro de digitação na tela de login é severidade Baixa e pode ser prioridade alta antes de um lançamento.

## Antes de abrir
- Reproduza pelo menos duas vezes e anote a frequência.
- Veja se já não foi registrado.
- Confirme o resultado esperado na história ou na regra, não no que *eu* acho que deveria acontecer. Se a regra não está clara, pergunte primeiro: isso é dúvida, não bug.

---

## Exemplo (fictício: TrilhaFit)

**Título:** [Lista de espera] Aluna é promovida da lista de espera mas não recebe notificação quando a aula começa em menos de 2 horas

| Campo | Valor |
|---|---|
| Ambiente | Staging, build 2.3.0 (412), Android 14, Pixel 7 |
| Conta / perfil | *carla.premium* (aluna Premium) |
| Severidade / Prioridade | Alta / a definir com o PO |
| Frequência | Sempre (3 de 3 tentativas) |
| Relacionados | História BK-111, caso TC-0231 |

**Pré-condições:** *Yoga, hoje 18:00* está lotada. *carla.premium* é a nº 1 da lista de espera. Horário atual: 16:30.

**Passos para reproduzir**
1. Entrar na web como *davi.basic*, que tem reserva confirmada em *Yoga, hoje 18:00*
2. Cancelar a reserva
3. No Android, verificar as notificações de *carla.premium*
4. Abrir *Minhas aulas* no app como *carla.premium*

**Resultado esperado:** *carla.premium* recebe a notificação "Abriu uma vaga: você está confirmada no Yoga das 18:00" (BK-111, critério de aceite 3: notificação em toda promoção, sem restrição de horário).
**Resultado obtido:** Nenhuma notificação chega. Em *Minhas aulas* a reserva aparece como *Confirmada*. Quando a aula começa em mais de 2 horas, a notificação chega normalmente.

**Evidência:** gravação de tela dos passos 2 a 4; resposta do `POST /bookings/{id}/cancel` com status 200.

**Observações:** a janela de 2 horas coincide com a regra de "cancelamento tardio"; a promoção pode estar reaproveitando essa condição para pular a notificação.
