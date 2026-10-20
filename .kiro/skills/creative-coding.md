---
inclusion: auto
name: creative-coding
description: Técnicas avançadas de creative coding para web — SVG animado, Canvas, efeitos visuais sem dependências externas. Usar quando criar ilustrações, animações de hero, efeitos de partículas ou elementos visuais diferenciados.
---

# Creative Coding — Técnicas Avançadas

> Baseado em: athevon/genjutsu + cloudai-x/threejs-skills (adaptado para HTML vanilla)

## Filosofia
Antes de escrever código de animação, definir uma **tese de interação**:
- O que o usuário deve SENTIR ao ver isso?
- Qual é o comportamento físico que imita? (fluido, mecânico, magnético)
- Como isso reforça a identidade da marca?

## SVG Animado — técnicas para hero sections

### Padrões de fundo reutilizáveis
```html
<!-- Grade técnica — ideal para mecânica/tech -->
<pattern id="grid" width="30" height="30" patternUnits="userSpaceOnUse">
  <path d="M 30 0 L 0 0 0 30" fill="none" stroke="#F97316" stroke-width="0.3" stroke-opacity="0.12"/>
</pattern>

<!-- Padrão de pontos -->
<pattern id="dots" width="20" height="20" patternUnits="userSpaceOnUse">
  <circle cx="2" cy="2" r="1.5" fill="#F97316" fill-opacity="0.08"/>
</pattern>
```

### Glow/Filter effects em SVG
```html
<defs>
  <filter id="glow">
    <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
    <feMerge>
      <feMergeNode in="coloredBlur"/>
      <feMergeNode in="SourceGraphic"/>
    </feMerge>
  </filter>
  <radialGradient id="bgGlow" cx="50%" cy="60%" r="50%">
    <stop offset="0%"   stop-color="#F97316" stop-opacity="0.12"/>
    <stop offset="100%" stop-color="#F97316" stop-opacity="0"/>
  </radialGradient>
</defs>
```

### Animações CSS puras para SVG
```css
/* Flutuação suave — para elementos hero */
@keyframes float {
  0%, 100% { transform: translateY(0) rotate(-1deg); }
  50%       { transform: translateY(-12px) rotate(1deg); }
}

/* Rotação contínua — engrenagens, spinners */
@keyframes spin-cw  { from { transform: rotate(0deg); }   to { transform: rotate(360deg); } }
@keyframes spin-ccw { from { transform: rotate(360deg); } to { transform: rotate(0deg); } }

/* Scan line — painel de diagnóstico */
@keyframes scanLine {
  0%   { transform: translateY(0);    opacity: 0.8; }
  100% { transform: translateY(180px); opacity: 0; }
}

/* Partículas/faíscas */
@keyframes sparkle {
  0%, 100% { opacity: 0; transform: scale(0.5); }
  50%       { opacity: 1; transform: scale(1) translate(var(--tx), var(--ty)); }
}

/* Speed lines */
@keyframes speedLine {
  0%   { transform: translateX(60px);   opacity: 0; }
  30%  { opacity: 0.6; }
  100% { transform: translateX(-200px); opacity: 0; }
}

/* Piscar — indicadores LED */
@keyframes blink {
  0%, 100% { opacity: 1; }
  50%       { opacity: 0.2; }
}
```

### Performance — regras para animações CSS
- `will-change: transform` em elementos que animam constantemente
- `transform-origin` explícito para rotações em SVG
- Usar `translate3d` ao invés de `translate` para acionar GPU
- Evitar animar `width`, `height`, `top`, `left` — sempre `transform`

## Cards flutuantes sobre ilustrações
```html
<!-- Card de status flutuante — posicionamento absoluto sobre SVG -->
<div class="absolute -top-4 -left-4 z-20 glass-card rounded-xl px-4 py-3 
            flex items-center gap-3"
     style="animation: float 3.5s ease-in-out infinite;">
  <div class="w-8 h-8 rounded-lg bg-green-500/20 flex items-center justify-center">
    <!-- ícone SVG inline -->
  </div>
  <div>
    <p class="text-white text-xs font-bold">Status OK</p>
    <p class="text-gray-400 text-[10px]">Subtítulo</p>
  </div>
</div>
```

## Gradientes no SVG
```html
<defs>
  <linearGradient id="barGradient" x1="0%" y1="0%" x2="100%" y2="0%">
    <stop offset="0%"   stop-color="#22c55e"/>  <!-- verde -->
    <stop offset="60%"  stop-color="#F97316"/>  <!-- laranja -->
    <stop offset="100%" stop-color="#ef4444"/>  <!-- vermelho -->
  </linearGradient>
</defs>
<rect x="10" y="0" width="84" height="10" fill="url(#barGradient)" rx="5"/>
```

## Texto no SVG — painel de dados
```html
<!-- Monospace para dados técnicos -->
<text x="10" y="16" 
      fill="#F97316" 
      font-size="8.5" 
      font-family="monospace" 
      font-weight="bold" 
      opacity="0.9">
  DIAGNÓSTICO OBD-II
</text>
```

## Padrões reutilizáveis por setor
| Setor | Elementos SVG | Animações |
|-------|---------------|-----------|
| Mecânica/Auto | Pistão, engrenagem, velocímetro, roda | spin, float, scan |
| Solar/Energia | Raios, painéis, ondas | pulse, float |
| Advocacia | Balança, colunas | fade, slide |
| Imobiliária | Construção, chave | float, pulse |
| Tech/SaaS | Circuitos, dados, dashboard | scan, blink, counter |
