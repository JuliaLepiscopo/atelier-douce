# Atelier Douce

> _Doceria — landing page institucional com cardápio e depoimentos._

Single-page institucional da doceria **Atelier Douce**, com hero, cardápio de 4 pratos especiais e seção de avaliações. Feita em **Vite + HTML + CSS + JavaScript vanilla**, com **jQuery** para interações e **ScrollReveal** para animações de scroll.

## Stack

- **[Vite 7](https://vite.dev)** — bundler e dev server
- **HTML5 + CSS3 + JavaScript vanilla** (sem framework)
- **[jQuery 3.7](https://jquery.com)** via CDN — menu mobile, scroll spy
- **[ScrollReveal](https://scrollrevealjs.org)** via CDN — animações ao rolar
- **[Font Awesome 6](https://fontawesome.com/)** via CDN — ícones
- **Poppins** via Google Fonts

## Estrutura

```
atelier-douce/
├── index.html               # única página: Home + Cardápio + Avaliações
├── script.js                # menu mobile + scroll spy + ScrollReveal
├── vite.config.js
├── package.json
└── src/
    ├── styles/
    │   ├── styles.css       # tokens (paleta oklch), tipografia, btn-default, social buttons
    │   ├── header.css       # navbar + menu mobile
    │   ├── home.css         # hero
    │   ├── menu.css         # grid de pratos
    │   ├── testimonials.css # depoimentos
    │   └── footer.css       # wave SVG + copyright
    └── images/              # logos, pratos, chef, avatars, waves, ilustrações
```

## Seções

| ID                | Conteúdo                                                                |
| ----------------- | ----------------------------------------------------------------------- |
| `#home`           | Hero com CTA, telefone e redes sociais                                  |
| `#menu`           | 4 pratos especiais (Crema Caramellata, Dolce Notturno, Uva Imperiale, Notte di Bacche) com imagem, descrição, rating e preço |
| `#testimonials`   | Chef + depoimentos de clientes com "Ver mais avaliações"                |

## Interações

- **Menu mobile** — botão hambúrguer alterna entre `fa-bars` e `fa-xmark`, abre o `#mobile_menu` (jQuery)
- **Scroll spy** — ao rolar, detecta a seção atual e marca o `nav-item` correspondente como `.active`
- **Header com sombra dinâmica** — `box-shadow` aparece quando há scroll
- **Ver mais avaliações** — botão remove `.hidden` do bloco `#maisFeedback` e dispara `ScrollReveal` na entrada
- **ScrollReveal** — `#cta`, `.dish`, `#testimonial_chef` e `.feedback` animam ao entrar na viewport

## Design system

- **Paleta**: definida em `:root` no [styles.css](src/styles/styles.css)
  - Primárias em `oklch` (lilás/roxo) + amarelo neon (`#ffe100`) + roxo escuro (`#8a0194`)
  - Neutras: branco e quase-preto
- **Tipografia**: Poppins em todos os pesos (100–900)
- **Componentes utilitários**: `.btn-default` (botão roxo com hover translateY), `.social-media-buttons`, `.section-title`, `.section-subtitle`
- **Estilos modulares**: cada seção tem seu próprio CSS importado via `@import` no [styles.css](src/styles/styles.css)

## Como rodar

```bash
npm install
npm run dev        # vite --host (acessível na rede local)
```

Outros comandos:
```bash
npm run build      # build de produção em dist/
npm run preview    # serve o build localmente
```
