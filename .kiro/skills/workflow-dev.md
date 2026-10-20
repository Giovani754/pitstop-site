---
inclusion: auto
name: workflow-dev
description: Workflow de desenvolvimento e deploy para projetos de sites de negócios locais. Padrões de commit, checklist antes do push, e processo de entrega ao cliente.
---

# Workflow de Desenvolvimento — Sites Negócios Locais

## Stack padrão deste projeto
- **HTML + Tailwind CDN + JS Vanilla** — arquivo único `index.html`
- **Deploy:** Netlify (conectado ao GitHub `Giovani754/pitstop-site`)
- **Push automático:** qualquer commit em `main` atualiza o site em <60s

## Checklist obrigatório antes de cada push

### Performance mobile
- [ ] `overflow-x: hidden` no `<html>` e `<body>`
- [ ] Nenhum `background-attachment: fixed` (usar `scroll`)
- [ ] Orbs de glow com tamanho responsivo (sem `w-[600px]` fixo)
- [ ] `-webkit-tap-highlight-color: transparent` em links
- [ ] Fundo `#080808` inline no `<head>` antes do Tailwind

### Animações
- [ ] IntersectionObserver com `threshold: 0.05`
- [ ] Safety-net setTimeout(1500ms) para revelar tudo se observer falhar
- [ ] `will-change: transform` em animações contínuas CSS
- [ ] Shimmer nos botões CTA principais
- [ ] Nunca desativar animações — otimizar, nunca remover

### Qualidade visual
- [ ] Glassmorphism nos cards
- [ ] Hover com borda laranja + glow nos cards
- [ ] Gradiente de texto nos destaques da headline
- [ ] Scroll indicator no hero
- [ ] FAB WhatsApp com pulse animation

### Código
- [ ] SVG icons inline (sem bibliotecas externas)
- [ ] Google Fonts com `rel="preconnect"`
- [ ] Schema.org LocalBusiness no `<head>`
- [ ] Meta tags OG completas
- [ ] Footer com copyright dinâmico via JS

## Padrão de mensagens de commit
```
feat: adiciona [funcionalidade]
fix: corrige [problema] no [onde]
style: ajusta [visual] na [seção]
perf: otimiza [o que] para mobile
refactor: reorganiza [estrutura]
```

## Comandos de deploy (executar nesta ordem)
```powershell
cd "c:\Users\giova\Documents\Outros-Negocios\teste site oficina"
git add index.html
git commit -m "feat/fix/style: descrição"
git push
```

## Estrutura de seções — ordem de conversão
Hero → Serviços → Diferenciais → Números → Depoimentos → Localização → CTA Final → Footer

## Próximos projetos — template adaptável
Ao criar novo site de negócio local:
1. Trocar nome, cores e tipografia
2. Adaptar ícones SVG para o setor
3. Reescrever copy focado na dor do cliente
4. Substituir métricas (anos, clientes, projetos)
5. Atualizar endereço, telefone e mapa
6. Novo repositório GitHub + Netlify em 5 min

## Faixa de preços e posicionamento
- **R$ 500–800:** Site padrão 1 página (este template)
- **R$ 800–1.200:** + formulário de contato funcional
- **R$ 1.200–1.500:** + painel admin básico ou integração WhatsApp API
- **Diferencial:** design premium visual que IA genérica não entrega
