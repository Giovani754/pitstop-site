---
inclusion: auto
name: gsap-animations
description: Use quando criar ou melhorar animações JavaScript com GSAP — scroll animations, timelines, staggers, ScrollTrigger. Aplica quando usuário pede animações de entrada, saída, scroll-driven ou interações animadas.
---

# GSAP Core — Skill Oficial GreenSock

> Fonte: https://github.com/greensock/gsap-skills (oficial GreenSock, MIT)

## Regra de ouro
**GSAP é grátis** — todos os plugins incluindo SplitText, MorphSVG, ScrollTrigger, Flip estão no pacote público `gsap`. Nenhum token ou assinatura necessária.

## CDN (para projetos HTML puro como este)
```html
<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/gsap.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/gsap@3/dist/ScrollTrigger.min.js"></script>
```

## Métodos principais
- `gsap.to(targets, vars)` — do estado atual para `vars` (mais usado)
- `gsap.from(targets, vars)` — de `vars` ao estado atual (entradas)
- `gsap.fromTo(targets, fromVars, toVars)` — início e fim explícitos
- `gsap.set(targets, vars)` — aplica imediatamente sem animação

## Propriedades essenciais
```js
gsap.to(".card", {
  x: 0,              // translateX (px)
  y: -20,            // translateY (px)
  scale: 1,          // scale
  opacity: 1,        // use autoAlpha para fade + visibility
  autoAlpha: 1,      // PREFERIR a opacity — zera visibility: hidden também
  duration: 0.6,     // segundos
  ease: "power3.out",// ver tabela abaixo
  stagger: 0.1,      // delay entre múltiplos elementos
  delay: 0.2,
});
```

## Easings recomendados
| Situação | Easing |
|----------|--------|
| Entrada padrão | `"power2.out"` |
| Entrada elegante | `"power3.out"` |
| Saída | `"power2.in"` |
| Premium/luxo | `"power4.inOut"` |
| Overshoot/bounce | `"back.out(1.7)"` |
| Elástico | `"elastic.out(1, 0.3)"` |
| Linear (spinners) | `"none"` |

## ScrollTrigger — animações no scroll
```js
gsap.registerPlugin(ScrollTrigger);

gsap.from(".section", {
  y: 50,
  autoAlpha: 0,
  duration: 0.8,
  ease: "power3.out",
  scrollTrigger: {
    trigger: ".section",
    start: "top 85%",   // dispara quando topo do elemento chega a 85% da viewport
    toggleActions: "play none none none",
  }
});
```

## Timeline — sequências
```js
const tl = gsap.timeline({ defaults: { ease: "power3.out", duration: 0.6 } });
tl.from(".hero-title",    { y: 30, autoAlpha: 0 })
  .from(".hero-subtitle", { y: 20, autoAlpha: 0 }, "-=0.3")  // 0.3s overlap
  .from(".hero-cta",      { scale: 0.9, autoAlpha: 0 }, "-=0.2");
```

## Stagger em cards/grids
```js
gsap.from(".card", {
  y: 40,
  autoAlpha: 0,
  duration: 0.7,
  ease: "power3.out",
  stagger: { amount: 0.4, from: "start" },
  scrollTrigger: { trigger: ".cards-grid", start: "top 80%" }
});
```

## Regras — nunca fazer
- ❌ Animar `width`, `height`, `top`, `left` — usar `x`, `y`, `scale`
- ❌ Usar `opacity` solo em fade — usar `autoAlpha`
- ❌ `background-attachment: fixed` com ScrollTrigger — quebra em iOS
- ❌ Múltiplos `from()` no mesmo elemento sem `immediateRender: false`

## Compatibilidade mobile
Usar `gsap.matchMedia()` para reduzir animações em `prefers-reduced-motion`:
```js
const mm = gsap.matchMedia();
mm.add("(prefers-reduced-motion: no-preference)", () => {
  // animações completas aqui
});
```
