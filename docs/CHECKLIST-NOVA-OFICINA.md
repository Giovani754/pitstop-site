# Checklist: nova oficina

Tudo que muda de cliente para cliente fica no objeto `OFICINA`, no topo do script do `index.html`.
Depois de trocar, copiar para `dist/` e fazer o deploy de prévia (ver `PAINEL.md`).

## O que trocar antes de publicar para um cliente real

Os dados atuais são de modelo (`modelo: true` no objeto, flag interna que não aparece na tela).

- [ ] **Nome, nome curto, tipo, bairro, cidade, UF** (`nome`, `nomeCurto`, `tipo`, `bairro`, `cidade`, `uf`).
- [ ] **Endereço** (`endereco.rua`, `cep`, `completo`, `referencia`) e **`geo`** (latitude e longitude reais, usadas no JSON-LD).
- [ ] **Telefone** (`telefone.exibe` e `telefone.tel`, só dígitos com DDI) e **WhatsApp** (`whatsapp`, só dígitos com DDI). Testar o botão no celular.
- [ ] **Horário de funcionamento** (`horarios`). Alimenta o "aberto agora", a lista e o JSON-LD.
- [ ] **Preços "a partir de"** de cada serviço em `hero.pontos[].preco` (o diagnóstico usa os mesmos). Confirmar com o dono; ajustar também textos e descrições dos serviços.
- [ ] **Fotos**: `heroFoto` e `heroFotoMobile` (versão vertical), `heroFotoDim`, os dois `<link rel="preload">` no `<head>` (mesmos caminhos) e `fotos.*.src` da seção "A oficina". Otimizar em WebP, salvar em `img/` e `dist/img/`, registrar a fonte em `docs/creditos-imagens.md`. Sem nenhuma foto em `fotos.*`, a seção "A oficina" some.
- [ ] **Selos da hero** (`hero.selos`): conferir se as promessas são verdadeiras para esta oficina (garantia em dias, peça com nota fiscal, orçamento antes).
- [ ] **Faixa de números** (`numeros`): vazia por padrão (a faixa não aparece). Só preencher com dados verificáveis (anos de oficina, carros atendidos...).
- [ ] **Avaliações** (`avaliacoes.lista`, itens `{ nome, texto, estrelas }`): só depoimentos reais, com autorização. Lista vazia = a seção não aparece e entra "Como a gente trabalha".
- [ ] **Avaliação no Google** (`googleReviewUrl`, `googleNota`, `googleTotalAvaliacoes`): link de avaliação do perfil da oficina, nota e total reais. Link vazio = sem a seção "Avalie a gente no Google"; nota e total vazios = sem a faixa com estrelas. Com tudo preenchido e `modelo: false`, o JSON-LD passa a incluir `aggregateRating`.
- [ ] **Mapa** (`endereco.mapaBusca`): texto que o Google Maps entende. Conferir se o pino cai no lugar certo.
- [ ] **Textos de cada seção** (`hero`, `servicos`, `processo`, `trabalho`, `oficina`, `orcamento`, `localizacao`, `diagnostico`): ajustar para a voz e os serviços do cliente.
- [ ] **`modelo: false`** (por último, depois de tudo acima).

## Antes de mostrar

- [ ] Buscar no HTML e no texto renderizado: `exemplo`, `demo`, `mock`, `placeholder`, `lorem`, `CNPJ`. Esperado: nenhuma ocorrência visível.
- [ ] Conferir em 360, 390, 768 e 1280: sem rolagem horizontal e sem erros no console.
- [ ] Rodar Lighthouse (mobile) e corrigir o que cair abaixo de 90.
