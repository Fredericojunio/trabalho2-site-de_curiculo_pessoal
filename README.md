# trabalho2-site-de_curiculo_pessoal# Site de Currículo Pessoal — Frederico Albino Junior

## Estudante
- **Nome completo:** Frederico Albino Junior
- **Turma:** 2º Ano — Licenciatura em Informática — Programação de Design Web

## Descrição do projeto
Site pessoal de currículo (portfólio), constituído por 5 páginas HTML interligadas, construído
**exclusivamente com HTML5 e CSS3 puro** — sem frameworks CSS (Bootstrap, Tailwind, etc.) e sem
JavaScript. Toda a interatividade (menu, destaque da página ativa, hover, validação de formulário)
é conseguida apenas com HTML e CSS (pseudo-classes, seletores e atributos nativos de validação).

### Como visualizar o site
1. Clonar ou descarregar este repositório.
2. Abrir o ficheiro `index.html` diretamente no navegador (não é necessário servidor).
3. Navegar pelo menu no topo para aceder às restantes páginas.

## Páginas do site
| Página | Ficheiro | Conteúdo |
|---|---|---|
| Início | `index.html` | Apresentação pessoal, tagline, call-to-action, vídeo e áudio de apresentação |
| Currículo | `about.html` | Formação académica, experiência, competências técnicas, tabela de proficiência, certificados |
| Portfólio | `portfolio.html` | Grelha de projetos (CSS Grid) e vídeo de demonstração via YouTube |
| Hobbies | `hobbies.html` | Cartões de hobbies organizados com Flexbox e faixa de áudio |
| Contacto | `contact.html` | Formulário completo com validação nativa HTML5 |

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
│   ├── img/        (fotos, ícones, certificados, capturas de projetos)
│   ├── video/       (vídeo local de apresentação, se usado)
│   ├── audio/        (ficheiros .mp3/.ogg usados na tag <audio>)
│   └── ficheiros/    (CV em PDF e outros anexos)
└── README.md
```

> **Nota importante:** o código HTML já referencia os ficheiros de imagem, vídeo e áudio nos
> caminhos corretos dentro de `assets/`. É necessário adicionar os ficheiros reais (fotos próprias,
> um pequeno vídeo `.mp4`/`.webm` e um áudio `.mp3`/`.ogg`) nessas pastas antes da entrega, e
> substituir o ID do vídeo do YouTube em `portfolio.html` pelo ID real de um vídeo do seu canal.

## Principais tags HTML e recursos CSS utilizados

### HTML5 semântico
- `<header>` / `<nav>` / `<main>` / `<section>` / `<article>` / `<aside>` / `<footer>` — organizam o
  documento em regiões semânticas, substituindo o uso indiscriminado de `<div>` ("div soup").
- `<figure>` / `<figcaption>` — associam uma imagem à sua legenda de forma semanticamente correta
  (usado nos certificados e projetos do portfólio).
- `<video controls poster>` com múltiplos `<source type="...">` — vídeo nativo com pré-visualização
  e suporte a mais de um formato de ficheiro.
- `<audio controls>` com `<source type="audio/mpeg">` — reprodução de áudio nativa do navegador.
- `<fieldset>` / `<legend>` — agrupam campos relacionados do formulário de contacto com um título
  semântico, melhorando a acessibilidade.
- `<label for="...">` — associa cada campo do formulário à sua descrição textual, essencial para
  leitores de ecrã e para permitir clicar no texto para focar o campo.

### Validação HTML5 nativa (sem JavaScript)
- `required` — impede o envio do formulário sem preencher o campo.
- `minlength` / `maxlength` — limitam o número de caracteres (nome e mensagem).
- `pattern` — valida o formato do número de telefone com expressão regular.
- `min` / `max` — limitam a data mínima selecionável e o intervalo de idade.
- `type="email"` — o navegador valida automaticamente o formato de email.
- `accept` — restringe os tipos de ficheiro aceites no campo de upload.

### CSS3 — layout
- **Flexbox** (`display:flex`, `flex-direction`, `flex-wrap`, `justify-content`, `align-items`) —
  usado no menu do cabeçalho e, de forma explícita e obrigatória, na grelha de cartões da página
  Hobbies.
- **CSS Grid** (`display:grid`, `grid-template-columns`, `repeat()`, `minmax()`, `gap`) — usado na
  grelha de projetos do Portfólio, criando um layout responsivo sem media queries adicionais.
- **`position: sticky`** — aplicado ao `<header>`, mantendo o menu visível durante o scroll. A
  diferença entre `static`, `relative`, `absolute`, `fixed` e `sticky` está explicada em comentário
  no topo de `css/estilo.css`.

### CSS3 — seletores e pseudo-classes/elementos
- Seletor descendente, filho direto (`>`), irmão adjacente (`+`) e 
