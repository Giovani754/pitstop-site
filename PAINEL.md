# PAINEL: site de oficina (PitStop, modelo)

Branch: `feat/skills-e-melhoria-1021`. Repo: Giovani754/pitstop-site.

## Feito (Fase 2, 21/10/2026)
- Site refeito sobre a mesma estrutura de seções, sem Tailwind CDN, com todo o texto/dados num objeto `OFICINA` no topo do script do `index.html`.
- Prints antes/depois em `docs/antes-depois/`. Diagnóstico em `docs/cara-de-ia.md`.

## Ajuste incremental (21/10/2026)
- Hero com carro SVG + scanner GSAP + 5 pontos clicáveis (balão com preço "a partir de" e botão Agendar no WhatsApp). `OFICINA.heroFoto` preenchido troca o carro por foto de fundo + lista de botões.
- Mapa com bloco de endereço de reserva, cabeçalho sólido, sem WhatsApp no cabeçalho do celular, SEO local (title, description, JSON-LD com geo).
- Valores "a partir de", geo (lat/lng) e endereço são EXEMPLO. Trocar no objeto `OFICINA`.
- Visto em Chrome headless (390, 360, 768, 1280). Lighthouse NÃO medido (não instalado).

## Prévia (deploy)
O deploy sai da pasta `dist/` (só `index.html`; não há pasta de imagens ainda). Depois de mexer no `index.html`, copiar para `dist/` e rodar, nesta pasta, sem `--prod`:
`cp index.html dist/index.html` e `npx netlify-cli deploy --dir dist --alias previa-oficina`
Prévia: https://previa-oficina--pitstop-previa.netlify.app
Se passar a ter fotos, criar `dist/img/` e copiar junto.
Antes: não há `netlify.toml` nem site Netlify ligado a este repo. Para criar prévia (precisa de login do Giovani):
`npx netlify-cli deploy --dir . --alias previa-oficina` (sem `--prod`).
Alternativa sem conta: abrir `index.html` direto no navegador.

## Falta o Giovani
- Fotos reais (fachada, equipe, serviço em andamento, bancada): colocar em `img/` e preencher `OFICINA.fotos.*.src`.
- Dados reais do cliente: nome, bairro, endereço, telefone, WhatsApp, horários, CNPJ, serviços.
- Avaliações reais do Google (nota, total, link, textos) e depois `exemplo:false`.
- Lighthouse real: não medido aqui (ver relatório).
