# PAINEL: site de oficina (PitStop, modelo)

Branch: `feat/skills-e-melhoria-1021`. Repo: Giovani754/pitstop-site.

## Feito (Fase 2, 21/10/2026)
- Site refeito sobre a mesma estrutura de seções, sem Tailwind CDN, com todo o texto/dados num objeto `OFICINA` no topo do script do `index.html`.
- Prints antes/depois em `docs/antes-depois/`. Diagnóstico em `docs/cara-de-ia.md`.

## Prévia (deploy)
BLOQUEADO: não há `netlify.toml` nem site Netlify ligado a este repo. Para criar prévia (precisa de login do Giovani):
`npx netlify-cli deploy --dir . --alias previa-oficina` (sem `--prod`).
Alternativa sem conta: abrir `index.html` direto no navegador.

## Falta o Giovani
- Fotos reais (fachada, equipe, serviço em andamento, bancada): colocar em `img/` e preencher `OFICINA.fotos.*.src`.
- Dados reais do cliente: nome, bairro, endereço, telefone, WhatsApp, horários, CNPJ, serviços.
- Avaliações reais do Google (nota, total, link, textos) e depois `exemplo:false`.
- Lighthouse real: não medido aqui (ver relatório).
