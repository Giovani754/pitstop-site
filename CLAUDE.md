# Site de oficina (HTML estático, index.html)

- Usar GSAP e a skill motion-design em todas as animações.
- Respeitar prefers-reduced-motion (gsap.matchMedia ou media query CSS).
- Animar só transform e opacity; nunca width, height, top, left, margin.
- Carregamento rápido no celular: pouco JS, GSAP por CDN com versão fixa, nada pesado acima da dobra.
- Nunca animação que atrapalhe ler telefone e endereço: eles ficam estáticos e sempre visíveis.
- threejs NÃO usar neste projeto (nem 3D, nem WebGL).
