de → refinamentos),
e não como um único commit final.
# Meu Currículo — Site Pessoal (HTML5 + CSS3 puro)

**Estudante:** Frederico Albino Junior 
**Turma:** 2º Ano — Licenciatura em Informática
**Disciplina:** Programação de Design Web
**Trabalho Prático I** — Site de Currículo Pessoal

---

### 🔗 Site online (GitHub Pages)
## **[👉 Acede ao site aqui](https://fredericojunio.github.io/trabalho2-site-de_curiculo_pessoal/)**
`https://fredericojunio.github.io/trabalho2-site-de_curiculo_pessoal/`

---

## Descrição do projeto

Site pessoal de currículo/portfólio composto por 5 páginas HTML interligadas,
estilizado exclusivamente com CSS3 puro (sem Bootstrap, Tailwind, Bulma ou
qualquer framework) e sem uma única linha de JavaScript. Toda a
interatividade (menu ativo, formulário, `<details>`) é conseguida apenas com
HTML5 e CSS3, através de seletores, pseudo-classes e elementos nativos.

### Como visualizar

1. Clonar ou descarregar este repositório.
2. Abrir o ficheiro `index.html` diretamente no navegador (não é necessário
   servidor nem instalação de dependências).
3. Navegar pelo site através do menu no topo, presente em todas as páginas.

> Nota: os ficheiros de vídeo/áudio locais referenciados em `assets/video/`
> e `assets/audio/` são placeholders — substituir pelos ficheiros reais do
> estudante antes da entrega final. O vídeo também está incorporado via
> YouTube (`<iframe>`) na Home como alternativa.

## Estrutura de pastas

```
meu-curriculo/
├── index.html
├── about.html
├── portfolio.html
├── hobbies.html
├── contact.html
├── css/
│   ├── estilo.css
│   └── responsivo.css
├── assets/
│   ├── img/
│   ├── video/
│   ├── audio/
│   └── ficheiros/
└── README.md
```

## Páginas do site

| Página | Conteúdo |
|---|---|
| `index.html` (Home) | Apresentação pessoal, avatar, tagline, resumo de competências, botão CTA para a página de contacto, vídeo de apresentação nativo (`<video>`) e incorporado via YouTube (`<iframe>`). |
| `about.html` (Currículo) | Formação académica e experiência em listas (`<ul>`/`<ol>`), tabela de competências técnicas com `colspan`/`rowspan`, certificados em `<figure>`/`<figcaption>`. |
| `portfolio.html` (Portfólio) | Grelha de 4 projetos em cartões, construída com **CSS Grid** (`grid-template-columns`, `repeat()`, `minmax()`, `gap`), vídeo de demonstração de um projeto. |
| `hobbies.html` (Hobbies) | Cartões de hobbies organizados com **Flexbox** (`flex-direction`, `flex-wrap`, `justify-content`, `align-items`) e faixa de áudio (`<audio>`). |
| `contact.html` (Contacto) | Formulário completo com todos os tipos de campo pedidos e validação nativa HTML5, agrupado em `<fieldset>`/`<legend>`. |

## Principais tags HTML e propriedades CSS utilizadas

### HTML semântico
- `<header>` / `<nav>` / `<main>` / `<section>` / `<article>` / `<footer>` — organizam o documento em regiões semânticas claras, melhorando a acessibilidade e o SEO, em substituição de "div soup".
- `<figure>` / `<figcaption>` — associam uma imagem à sua legenda de forma semântica (certificados e projetos).
- `<video>` com `controls`, `poster` e `<source type="...">` — permite reprodução nativa de vídeo com pré-visualização e múltiplos formatos de fallback.
- `<audio>` com `controls` e `<source type="...">` — reprodução nativa de áudio com fallback de formato.
- `<details>` / `<summary>` — mostra/esconde conteúdo extra (link do YouTube) sem qualquer JavaScript.
- `<fieldset>` / `<legend>` — agrupam campos relacionados do formulário com um título acessível.
- `<table>` com `<thead>`/`<tbody>`, `colspan`, `rowspan` — organiza a tabela de competências de forma estruturada.

### CSS — seletores e pseudo-classes
- **Seletores avançados**: descendentes (`.menu a`), filho direto (`.menu > li > a`), irmão adjacente (`h2 + p`) e de atributo (`input[type="email"]`, `a[href^="http"]`) — permitem estilizar elementos com precisão, sem adicionar classes extra a cada um.
- **Pseudo-classes**: `:hover`, `:focus`, `:first-child`, `:last-child`, `:nth-child()`, `:checked`, `:valid`/`:invalid` — usadas para feedback visual e para estilizar radios/checkboxes customizados apenas com CSS.
- **Pseudo-elementos**: `::before` e `::after` — usados no ícone decorativo do logótipo e no sublinhado animado dos links do menu.

### CSS — layout
- **Flexbox** (`hobbies.html`) — `display: flex`, `flex-wrap: wrap`, `justify-content: space-between`, `align-items: stretch` distribuem os cartões de hobbies de forma flexível em qualquer largura de ecrã.
- **CSS Grid** (`portfolio.html`) — `display: grid`, `grid-template-columns: repeat(auto-fit, minmax(260px, 1fr))`, `gap` criam uma grelha de cartões que se adapta automaticamente ao número de colunas possível.
- **`position: sticky`** — aplicado ao `<header>` para que o menu permaneça visível durante o scroll. A diferença entre `static`, `relative`, `absolute`, `fixed` e `sticky` está explicada em comentário no início da secção de header em `css/estilo.css`.

### CSS — responsividade
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` presente em todas as páginas.
- Duas media queries principais em `css/responsivo.css`: `max-width: 480px` (telemóvel) e `max-width: 768px` (tablet), seguindo abordagem **mobile-first** (estilos base pensados para ecrã pequeno, depois ajustados/ampliados).
- Unidades relativas (`rem`, `%`, `vw`/`vh`) combinadas com unidades fixas (`px`) sempre que a precisão visual o justifica (ex: bordas de 1px).

### CSS — estilo visual avançado
- **Variáveis CSS** (`:root`) — centralizam cores, tipografia e espaçamentos, facilitando a consistência e manutenção do design.
- **Transições** (`transition`) — usadas nos links do menu, botões e cartões, para uma resposta suave ao `:hover`/`:focus`.
- **Animação** (`@keyframes surgir`) — efeito discreto de entrada (fade + slide) aplicado à secção hero da Home.
- **Gradientes e sombras** — `linear-gradient` no fundo do hero; `box-shadow` em cartões e header; `text-shadow` reservado para destaques tipográficos.
- **Tipografia** — pilha de fontes (`font-family`) com Google Fonts (Poppins para títulos, Inter para o corpo) e alternativas de sistema como fallback.

## Formulário e validação (contact.html)

Todos os campos usam apenas atributos nativos do HTML5 para validação —
sem JavaScript nem bibliotecas:

- `required` — nome, email, motivo, mensagem.
- `minlength` / `maxlength` — nome (mín. 3) e mensagem (mín. 10, máx. 600).
- `pattern` — telefone, validado com expressão regular para números moçambicanos.
- `min` / `max` — idade (15 a 99).
- `type="email"` — validação automática do formato de email pelo navegador.
- `type="file"` com `accept=".pdf"` — restringe o tipo de ficheiro aceite no anexo.
- `<select>` obrigatório e grupos de `radio`/`checkbox` estilizados via CSS (sem aparência padrão do navegador, usando a técnica de esconder o input e estilizar o `<label>` associado com `:checked`).

## Acessibilidade

- Todas as imagens têm atributo `alt` descritivo.
- Todos os campos do formulário têm `<label for="...">` associado ao respetivo `id`.
- Uso de `aria-label`, `aria-current="page"`, `aria-labelledby` e `role="radiogroup"`/`role="group"` onde relevante.
- Hierarquia de headings coerente: um único `<h1>` por página.
- Contraste de cor cuidado entre texto e fundo em todas as secções.

## Notas finais

Este é um projeto académico desenvolvido para a disciplina de Programação
de Design Web. Não utiliza frameworks de CSS, geradores automáticos de site
nem JavaScript, conforme exigido no enunciado do trabalho.
