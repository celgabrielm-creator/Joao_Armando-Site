# João Armando | Site Oficial

Site estático de divulgação artística desenvolvido com **HTML5 semântico**, **CSS3 nativo** e **JavaScript vanilla**, sem dependências de frameworks ou bibliotecas externas.

---

## Stack

| Camada | Tecnologia |
|---|---|
| Markup | HTML5 com atributos ARIA e Open Graph |
| Estilo | CSS3 — Custom Properties, Grid, Flexbox, Backdrop Filter |
| Script | JavaScript ES6+ — IntersectionObserver API, DOM manipulation |
| Tipografia | Google Fonts — Inter (400/500/700/800/900) + Playfair Display (700/900) |
| Versionamento | Git + GitHub |

---

## Estrutura do projeto

```
Joao_Armando-Site/
├── index.html          # Página principal
├── about.html          # Página sobre o artista
├── css/
│   └── style.css       # Folha de estilos global
└── imagens/
    ├── foto-3.jpeg
    ├── foto-4.jpeg
    ├── foto-5.jpeg
    ├── foto-6.jpeg
    ├── diamante-5.jpeg
    ├── diamante-6.jpeg
    ├── favicon.png
    ├── spotify.svg
    ├── instagram.png
    └── ruido.png       # Textura de ruído para background
```

---

<<<<<<< HEAD
O e-mail oficial para parcerias é `joaoarmando.faria@gmail.com`.
=======
## Arquitetura CSS

O projeto utiliza **CSS Custom Properties** (variáveis nativas) definidas no `:root` como design tokens:

```css
:root {
  --bg: #050508;
  --bg-soft: #0e0d18;
  --text: #f7f4ff;
  --muted: #b8b1c9;
  --accent: #8b5cf6;
  --accent-2: #21e6c1;
  --gold: #d7b66d;
}
```

O layout é construído inteiramente com **CSS Grid** e **Flexbox**, sem uso de frameworks como Bootstrap ou Tailwind. O background é composto por múltiplas camadas via `radial-gradient`, `linear-gradient` e `url()` em uma única declaração `background`, combinados com textura de ruído PNG para profundidade visual.

---

## JavaScript

O script é **inline no final do `<body>`** e cobre dois comportamentos:

**1. Menu mobile com acessibilidade:**
```js
const toggle = document.querySelector('.menu-toggle');
const menu = document.querySelector('#menu');
toggle.addEventListener('click', () => {
  const open = menu.classList.toggle('is-open');
  toggle.setAttribute('aria-expanded', open ? 'true' : 'false');
});
```

**2. Animações de entrada com IntersectionObserver:**
```js
const observer = new IntersectionObserver((entries) => {
  entries.forEach((entry) => {
    if (entry.isIntersecting) entry.target.classList.add('visible');
  });
}, { threshold: 0.12 });
```

Elementos com a classe `.reveal` iniciam com `opacity: 0` e `transform: translateY(26px)`, e recebem a classe `.visible` ao entrar no viewport, disparando a transição CSS.

---

## Responsividade

Dois breakpoints via `@media`:

| Breakpoint | Comportamento |
|---|---|
| `max-width: 920px` | Menu hambúrguer, grids colapsam para 1 coluna, hero reestruturado |
| `max-width: 620px` | Botões em largura total, feature-player em coluna única, galeria simplificada |

O tamanho de `h1` utiliza `clamp()` para escalonamento fluido:
```css
font-size: clamp(4rem, 12vw, 9rem);
```

---

## SEO e acessibilidade

- Meta tags `description`, `author` e **Open Graph** (`og:title`, `og:description`, `og:image`)
- Atributos `aria-label`, `aria-controls`, `aria-expanded` e `aria-labelledby` nas seções e navegação
- Links externos com `rel="noopener noreferrer"` e `target="_blank"`
- Imagens com `alt` descritivos; ícones decorativos com `alt=""`
- Estrutura semântica com `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`, `<blockquote>`

---

## Como executar localmente

```bash
# Clonar o repositório
git clone https://github.com/armando-obala/Joao_Armando-Site.git
cd Joao_Armando-Site

# Abrir com Live Server (VS Code) ou qualquer servidor HTTP estático
# Exemplo com Python:
python -m http.server 3000
```

Acesse `http://localhost:3000` no navegador.

> Não recomendado abrir `index.html` direto pelo sistema de arquivos (`file://`) pois alguns recursos de fontes e background podem não carregar corretamente em certos navegadores.

---

## Links do artista

- [Spotify](https://open.spotify.com/intl-pt/artist/1fcetspB9sifVRF2FHH1wx)
- [YouTube](https://youtube.com/@joaoarmando_)
- [Instagram](https://www.instagram.com/armandooj_)

---

## Contato e parcerias

📧 joaoarmando.faria@gmail.com

---

## Licença

Todos os direitos reservados © 2026 João Armando. Conteúdo e identidade visual de uso exclusivo para divulgação artística.
>>>>>>> 445d51ac16e3e3c1cdb1cb9d8880bf08f5f9bbbf
