# Skills instaladas (21/10/2026)

Instalação manual por git clone + cópia (sem `npx skills add`). Nenhum script das skills foi executado. Todos os arquivos foram lidos antes (resultado: limpo).

| Skill | Repositório | Commit (hash) | Data | O que foi copiado | Onde |
|---|---|---|---|---|---|
| gsap-core | https://github.com/greensock/gsap-skills | aed9cfd3277740755f6bfc1155c7aa645403b760 | 21/10/2026 | skills/gsap-core/SKILL.md | .claude/skills/gsap-core/ |
| gsap-timeline | idem | aed9cfd3277740755f6bfc1155c7aa645403b760 | 21/10/2026 | skills/gsap-timeline/SKILL.md | .claude/skills/gsap-timeline/ |
| gsap-scrolltrigger | idem | aed9cfd3277740755f6bfc1155c7aa645403b760 | 21/10/2026 | skills/gsap-scrolltrigger/SKILL.md | .claude/skills/gsap-scrolltrigger/ |
| gsap-performance | idem | aed9cfd3277740755f6bfc1155c7aa645403b760 | 21/10/2026 | skills/gsap-performance/SKILL.md | .claude/skills/gsap-performance/ |
| motion-design | https://github.com/LottieFiles/motion-design-skill | f9a8a041b85185ee4881b3471d3415e939aac772 | 21/10/2026 | skills/motion-design/ inteira (SKILL.md, director/, patterns/, reference/) | .claude/skills/motion-design/ |
| design-dna | https://github.com/zanwei/design-dna | 593e39bc9e3652734653bd75544a333d7d43615e | 21/10/2026 | SKILL.md, references/ e scripts/ (color-math, measure-colors, verify, package.json) | .claude/skills/design-dna/ |

Não copiado de propósito:
- gsap-react: o projeto é HTML estático, sem React/Next. Também ficaram de fora gsap-frameworks, gsap-plugins e gsap-utils (não pedidos).
- design-dna: READMEs (inclusive traduzidos), imagens de docs/ e teste de scripts/. Os scripts exigem `npm install` (pacote sharp) só se alguém rodar a medição de cores; ela não é executada automaticamente.
- threejs-skills (https://github.com/CloudAI-X/threejs-skills, commit 0e181866f095b5f06d005133876e926515390d95): NÃO ativa neste projeto. Fica na biblioteca premium em `Vykto/skills-e-conhecimento/skills-premium/threejs/`, para projeto premium com 3D.

Já existiam antes, não mexidos: `.agents/skills/` (gsap-*) e `skills-lock.json` (instalador de terceiros, untracked, fora deste commit) e `.kiro/`.
