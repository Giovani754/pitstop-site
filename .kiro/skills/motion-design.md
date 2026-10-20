---
inclusion: auto
name: motion-design
description: Aplica princípios profissionais de motion design em todas as animações. Usar sempre que criar qualquer animação, transição, micro-interação, estado de loading, ou efeito visual. Define timing, easing e coreografia antes de escrever código.
---

# Motion Design — Princípios Profissionais

> Fonte: https://github.com/LottieFiles/motion-design-skill (oficial LottieFiles, MIT)

## Checklist antes de qualquer animação (8 passos)
1. **Emoção alvo?** — alegria, calma, urgência, elegância
2. **Personalidade de movimento?** — Playful, Premium, Corporate, Energetic
3. **Propriedade principal?** — posição, escala, rotação, opacidade
4. **Duração?** — ver tabela abaixo
5. **Easing?** — entrada=desacelera, saída=acelera
6. **Elemento herói?** — entra primeiro ou mais proeminente
7. **Camadas secundária + ambiente?** — adiciona riqueza
8. **Regra 1/3?** — sem mais de 1/3 dos elementos em movimento simultâneo

## Personalidade de movimento — escolher UMA por projeto
| Arquétipo | Duração | Easing | Overshoot | Quando usar |
|-----------|---------|--------|-----------|-------------|
| **Playful** | 150–300ms | ease-out-back | 10–20% | diversão, jovial, bounce |
| **Premium** | 350–600ms | cubic-bezier(0.4,0,0.2,1) | 0% | luxo, elegância, sofisticação |
| **Corporate** | 200–400ms | cubic-bezier(0.2,0,0,1) | 0–3% | negócios, dashboard, profissional |
| **Energetic** | 100–250ms | ease-out-expo | 15–30% | dinâmico, bold, esportivo |

> **Para sites de mecânica/automotive:** usar **Energetic** nos destaques + **Premium** no texto.

## Tabela de duração por elemento
| Elemento | Duração |
|----------|---------|
| Tooltip / micro-feedback | 80–120ms |
| Botão / toggle | 120–180ms |
| Ícone | 150–250ms |
| Card entrada/saída | 200–350ms |
| Modal / dialog | 300–400ms |
| Transição de página | 400–600ms |
| Reveal dramático (hero) | 600–1200ms |

**Regra:** Entradas 30–50% mais longas que saídas. Entradas importam mais.

## Easing por direção
- **Entrada** → desacelera (rápido no início, suave no pouso): `ease-out`
- **Saída** → acelera (suave no início, rápido na saída): `ease-in`
- **Na tela** → suave nos dois: `ease-in-out`
- **Loops ambientes** → `sine-in-out`

## Três camadas de motion (animação plana = camada faltando)
- **Primária**: ação principal que o usuário segue (card entrando)
- **Secundária**: riqueza de suporte (sombra, ícone se deslocando)
- **Ambiente**: vida de fundo (gradiente pulsando, brilho sutil)

## Coreografia — stagger budgets
| Padrão | Delay entre itens | Budget total |
|--------|-------------------|-------------|
| Micro cascata | 20–40ms | <200ms |
| Padrão (cards) | 50–100ms | <400ms |
| Dramático (hero) | 100–200ms | <600ms |

> Máximo absoluto de stagger total: **500ms**

## Emoção → Movimento
| Emoção | Easing | Duração |
|--------|--------|---------|
| Alegria | ease-out-back | 200–400ms |
| Calma | sine ease-in-out | 500–1000ms |
| Urgência | ease-out | 100–200ms |
| Elegância | cubic-bezier(0.4,0,0.2,1) | 400–700ms |
| Surpresa | ease-out-expo | 150–300ms |

## Regras críticas — nunca quebrar
1. ❌ **Nunca linear** para movimento espacial — sempre usar curvas
2. ❌ **Nunca só opacity** para mudanças de estado importantes — combinar com posição ou escala
3. ❌ **Nunca mais de 1/3 da tela** de movimento sem keyframe intermediário
4. ✅ **Sempre três camadas** — primária + secundária + ambiente
