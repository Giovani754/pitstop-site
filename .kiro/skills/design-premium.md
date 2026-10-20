---
inclusion: auto
name: design-premium
description: Padrões de design visual premium para sites de negócios locais brasileiros. Glassmorphism, dark mode, gradientes, tipografia e hierarquia visual de alto padrão. Usar em todo projeto de site.
---

# Design Premium — Padrões Visuais

> Baseado em: zanwei/design-dna + athevon/genjutsu + análise dos projetos Invictto Motors e Carrera Import

## Identidade visual deste projeto
- **Cor primária:** `#F97316` (Laranja Âmbar)
- **Fundo:** `#080808` (Preto Piano)
- **Tipografia display:** Rajdhani (bold, uppercase para títulos)
- **Tipografia corpo:** Inter (400/500/600)
- **Estilo:** Dark Premium Industrial — mecânico, energético, confiável

## Glassmorphism — padrão obrigatório em cards
```css
.glass-card {
  background: rgba(255,255,255,0.04);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255,255,255,0.10);
  box-shadow: 0 20px 40px rgba(0,0,0,0.4);
}
/* Hover sempre com borda laranja + glow */
.glass-card:hover {
  border-color: rgba(249,115,22,0.35);
  box-shadow: 0 20px 50px rgba(0,0,0,0.6), 0 0 30px rgba(249,115,22,0.12);
}
```

## Gradiente de texto — para palavras de destaque
```css
.text-gradient {
  background: linear-gradient(135deg, #FB923C, #F97316, #EA6C00);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

## Shimmer em botões CTA — obrigatório no botão principal
```css
.btn-shimmer {
  background: linear-gradient(90deg, #EA6C00 0%, #F97316 30%, #FFBB85 50%, #F97316 70%, #EA6C00 100%);
  background-size: 200% auto;
  animation: shimmer 3s linear infinite;
  color: #080808;
  font-weight: 700;
}
@keyframes shimmer {
  from { background-position: -200% 0; }
  to   { background-position:  200% 0; }
}
```

## Hierarquia de seções — estrutura padrão de conversão
1. **Hero** — Headline impacto + subheadline + 2 CTAs + métricas de credibilidade
2. **Serviços** — Grid 3 colunas com cards glass + preço ou CTA por card
3. **Diferenciais** — Split layout: texto sticky esquerda + cards empilhados direita
4. **Números** — Counters animados com JS (IntersectionObserver)
5. **Depoimentos** — 3 cards com estrelas + avatar de iniciais
6. **Localização** — Grid: informações + mapa iframe
7. **CTA Final** — Gradiente escuro → laranja, headline urgência, botão WhatsApp grande
8. **Footer** — 3 colunas + redes sociais + copyright automático

## Cores de suporte
```
Laranja principal:  #F97316
Laranja escuro:     #EA6C00
Laranja claro:      #FB923C
Laranja glow:       rgba(249,115,22,0.15)
Fundo:              #080808
Card escuro:        #0A0A0A / #0D0D0D
Borda sutil:        rgba(255,255,255,0.08)
Texto principal:    #e5e5e5
Texto secundário:   #9ca3af (gray-400)
Texto muted:        #6b7280 (gray-500)
```

## Regras de responsividade mobile — NUNCA ESQUECER
- ✅ `overflow-x: hidden` no `<html>` e `<body>`
- ✅ `-webkit-tap-highlight-color: transparent` em todos os links
- ✅ `background-attachment: scroll` (NUNCA `fixed` — quebra iOS)
- ✅ Orbs de glow com `max-width: 60vw` para não vazar
- ✅ `will-change: transform` em animações CSS contínuas
- ✅ Testar `IntersectionObserver` com `threshold: 0.05` no mobile

## Microinterações obrigatórias
- Cards: `transform: scale(1.02)` no hover com `transition: 0.3s`
- Ícone nos cards: `background: rgba(cor, 0.20)` no hover (era 0.10)
- Links de nav: pseudo-elemento `::after` com underline animado
- FAB WhatsApp: pulse animation + tooltip no hover
- Scroll indicator: `animate-float` + `animate-bounce` no inner dot

## Tipografia — escala de tamanhos
```css
/* Hero headline — clamp para responsividade */
font-size: clamp(2.5rem, 6vw, 5rem);
line-height: 1.05;

/* Section titles */
font-size: clamp(2rem, 4vw, 3.5rem);

/* Card titles */
font-size: 1.25rem; /* text-xl */

/* Body */
font-size: 0.875rem; /* text-sm */
line-height: 1.625; /* leading-relaxed */
```
