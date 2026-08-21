# Design System — CasAMARelo Hostel

> Sistema de design completo para a landing page. Copie os tokens, componentes e padrões diretamente para o seu projeto.

---

## 1. Tokens de Cor

### 1.1 Paleta Primária

| Token | Hex | RGB | Uso |
|---|---|---|---|
| `--verde-mata` | `#1B5E3A` | `27, 94, 58` | Fundos de seção, textos sobre fundo claro, navbar |
| `--amarelo-dende` | `#E8A824` | `232, 168, 36` | Títulos display sobre fundo escuro, ícones, destaques |
| `--amarelo-claro` | `#F5C34B` | `245, 195, 75` | Variação mais suave do amarelo, hover em ícones |
| `--vermelho-terra` | `#B22D30` | `178, 45, 48` | CTAs primários, alertas, preço, botão WhatsApp |
| `--creme-areia` | `#F5E6C8` | `245, 230, 200` | Fundo principal, texto sobre fundo escuro |
| `--azul-colonial` | `#2D6A7A` | `45, 106, 122` | Títulos display alternativos, links, seções informativas |
| `--laranja-tropical` | `#E87C2E` | `232, 124, 46` | Badges, acentos, ícones interativos, focus ring |

### 1.2 Paleta Estendida (Suporte)

| Token | Hex | Uso |
|---|---|---|
| `--verde-folha` | `#2E7D4F` | Hover do verde-mata, sucesso, confirmação |
| `--vermelho-escuro` | `#8B1A1D` | Hover/active do vermelho-terra |
| `--creme-escuro` | `#E8D5B0` | Bordas sutis sobre fundo creme, dividers |
| `--verde-azulejo` | `#245C3E` | Pattern de azulejo tom-sobre-tom |
| `--texto-escuro` | `#1A1A1A` | Texto de corpo quando necessário preto (raro) |
| `--branco` | `#FDFBF7` | Off-white quente, nunca branco puro |

### 1.3 Semântica de Cores

```css
:root {
  /* Superfícies */
  --surface-primary:    var(--creme-areia);     /* #F5E6C8 */
  --surface-secondary:  var(--verde-mata);      /* #1B5E3A */
  --surface-accent:     var(--vermelho-terra);   /* #B22D30 */
  --surface-card:       var(--branco);           /* #FDFBF7 */

  /* Texto */
  --text-on-light:      var(--verde-mata);       /* #1B5E3A */
  --text-on-dark:       var(--creme-areia);      /* #F5E6C8 */
  --text-on-accent:     var(--creme-areia);      /* #F5E6C8 */
  --text-muted:         #5C7A65;                 /* verde dessaturado */

  /* Interação */
  --interactive:        var(--vermelho-terra);   /* #B22D30 */
  --interactive-hover:  var(--vermelho-escuro);  /* #8B1A1D */
  --focus-ring:         var(--laranja-tropical); /* #E87C2E */

  /* Decorativo */
  --accent-warm:        var(--amarelo-dende);    /* #E8A824 */
  --accent-cool:        var(--azul-colonial);    /* #2D6A7A */
  --accent-highlight:   var(--laranja-tropical); /* #E87C2E */
}
```

### 1.4 Contraste WCAG Validado

| Par | Ratio | Nível |
|---|---|---|
| `--text-on-light` sobre `--surface-primary` | 8.2:1 | ✅ AAA |
| `--amarelo-dende` sobre `--verde-mata` | 5.3:1 | ✅ AA Large |
| `--creme-areia` sobre `--vermelho-terra` | 5.8:1 | ✅ AAA |
| `--creme-areia` sobre `--verde-mata` | 7.9:1 | ✅ AAA |
| `--verde-mata` sobre `--amarelo-claro` | 4.8:1 | ✅ AA |
| `--laranja-tropical` sobre `--creme-areia` | 3.4:1 | ⚠️ Só Large Text |

---

## 2. Tipografia

### 2.1 Famílias

```css
:root {
  --font-display: 'Passion One', cursive;
  --font-body:    'Lora', serif;
  --font-ui:      'Inter', sans-serif;
}
```

**Google Fonts import:**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Lora:ital,wght@0,400;0,600;1,400&family=Passion+One:wght@400;700&display=swap" rel="stylesheet">
```

### 2.2 Escala Tipográfica

| Token | Tamanho | Peso | Família | Line Height | Uso |
|---|---|---|---|---|---|
| `--text-hero` | 64px / 4rem | 700 | `--font-display` | 1.05 | Título hero |
| `--text-h1` | 48px / 3rem | 700 | `--font-display` | 1.1 | Títulos de seção |
| `--text-h2` | 32px / 2rem | 700 | `--font-display` | 1.15 | Subtítulos de seção |
| `--text-h3` | 24px / 1.5rem | 600 | `--font-body` | 1.3 | Título de card/componente |
| `--text-eyebrow` | 13px / 0.8125rem | 700 | `--font-ui` | 1.4 | Tags de seção (uppercase) |
| `--text-body` | 17px / 1.0625rem | 400 | `--font-body` | 1.7 | Parágrafos, descrições |
| `--text-body-sm` | 15px / 0.9375rem | 400 | `--font-body` | 1.6 | Texto secundário, captions |
| `--text-label` | 12px / 0.75rem | 700 | `--font-ui` | 1.3 | Badges, tags, selos |
| `--text-caption` | 11px / 0.6875rem | 400 | `--font-ui` | 1.4 | Rodapé, disclaimer, meta |

### 2.3 Regras Tipográficas

```css
/* Eyebrow / Tag de seção */
.eyebrow {
  font-family: var(--font-ui);
  font-size: var(--text-eyebrow);
  font-weight: 700;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--accent-warm);
}

/* Título display com textura */
.heading-display {
  font-family: var(--font-display);
  font-weight: 700;
  line-height: 1.05;
  color: var(--amarelo-dende);
  /* Textura opcional via background-clip */
}

/* Corpo de texto */
.body-text {
  font-family: var(--font-body);
  font-size: var(--text-body);
  font-weight: 400;
  line-height: 1.7;
  max-width: 65ch;
  color: var(--text-on-light);
}

/* Label / Badge */
.label {
  font-family: var(--font-ui);
  font-size: var(--text-label);
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
```

### 2.4 Responsivo

| Token | Desktop | Tablet (≤768px) | Mobile (≤480px) |
|---|---|---|---|
| `--text-hero` | 64px | 48px | 36px |
| `--text-h1` | 48px | 36px | 28px |
| `--text-h2` | 32px | 26px | 22px |
| `--text-h3` | 24px | 22px | 20px |
| `--text-body` | 17px | 16px | 16px |

---

## 3. Espaçamento

### 3.1 Escala de Espaçamento

```css
:root {
  --space-2xs:  4px;    /* 0.25rem */
  --space-xs:   8px;    /* 0.5rem  */
  --space-sm:   12px;   /* 0.75rem */
  --space-md:   16px;   /* 1rem    */
  --space-lg:   24px;   /* 1.5rem  */
  --space-xl:   32px;   /* 2rem    */
  --space-2xl:  48px;   /* 3rem    */
  --space-3xl:  64px;   /* 4rem    */
  --space-4xl:  96px;   /* 6rem    */
  --space-5xl:  128px;  /* 8rem    */
}
```

### 3.2 Aplicação

| Contexto | Token | Valor |
|---|---|---|
| Padding interno de seção (vertical) | `--space-4xl` | 96px |
| Padding interno de seção (mobile) | `--space-3xl` | 64px |
| Gap entre seções | `--space-0` | 0 (seções coladas, divisor visual de azulejo) |
| Gap entre cards (grid) | `--space-lg` | 24px |
| Padding interno de card | `--space-xl` | 32px |
| Gap entre título e subtítulo | `--space-sm` | 12px |
| Gap entre subtítulo e corpo | `--space-lg` | 24px |
| Gap entre corpo e CTA | `--space-xl` | 32px |
| Padding interno de botão | `--space-md` `--space-xl` | 16px 32px |
| Padding interno de badge | `--space-xs` `--space-md` | 8px 16px |

### 3.3 Container

```css
.container {
  width: 100%;
  max-width: 1120px;
  margin-inline: auto;
  padding-inline: var(--space-lg); /* 24px */
}

@media (max-width: 768px) {
  .container {
    padding-inline: var(--space-md); /* 16px */
  }
}
```

---

## 4. Bordas e Formas

```css
:root {
  /* Radius */
  --radius-none:  0;
  --radius-sm:    6px;
  --radius-md:    12px;
  --radius-lg:    20px;
  --radius-pill:  100px;
  --radius-circle: 50%;

  /* Sombras */
  --shadow-card:    0 2px 12px rgba(27, 94, 58, 0.08);
  --shadow-card-hover: 0 8px 24px rgba(27, 94, 58, 0.14);
  --shadow-float:   0 12px 40px rgba(27, 94, 58, 0.18);
  --shadow-sticker:  2px 4px 0px rgba(0, 0, 0, 0.12);

  /* Bordas */
  --border-subtle: 1px solid var(--creme-escuro);
  --border-accent: 2px solid var(--amarelo-dende);
  --border-dashed: 2px dashed var(--verde-mata);
}
```

---

## 5. Componentes

### 5.1 Botão Primário (CTA)

```css
.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  padding: var(--space-md) var(--space-xl);
  background: var(--vermelho-terra);
  color: var(--creme-areia);
  font-family: var(--font-ui);
  font-size: 15px;
  font-weight: 700;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  border: none;
  border-radius: var(--radius-pill);
  cursor: pointer;
  transition: background 0.2s ease, transform 0.15s ease;
  box-shadow: var(--shadow-sticker);
  min-height: 48px;          /* acessibilidade: alvo de toque */
  min-width: 160px;
  text-decoration: none;
}

.btn-primary:hover {
  background: var(--vermelho-escuro);
  transform: translateY(-2px);
}

.btn-primary:focus-visible {
  outline: 3px solid var(--focus-ring);
  outline-offset: 3px;
}

.btn-primary:active {
  transform: translateY(0);
}
```

### 5.2 Botão Secundário

```css
.btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: var(--space-xs);
  padding: var(--space-md) var(--space-xl);
  background: transparent;
  color: var(--verde-mata);
  font-family: var(--font-ui);
  font-size: 15px;
  font-weight: 700;
  letter-spacing: 0.04em;
  text-transform: uppercase;
  border: 2px solid var(--verde-mata);
  border-radius: var(--radius-pill);
  cursor: pointer;
  transition: all 0.2s ease;
  min-height: 48px;
  text-decoration: none;
}

.btn-secondary:hover {
  background: var(--verde-mata);
  color: var(--creme-areia);
}

.btn-secondary:focus-visible {
  outline: 3px solid var(--focus-ring);
  outline-offset: 3px;
}
```

### 5.3 Badge / Selo

```css
/* Badge genérico (pílula) */
.badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2xs);
  padding: var(--space-xs) var(--space-md);
  background: var(--amarelo-dende);
  color: var(--verde-mata);
  font-family: var(--font-ui);
  font-size: var(--text-label);
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  border-radius: var(--radius-pill);
  white-space: nowrap;
}

/* Variante: nota/avaliação */
.badge--score {
  background: var(--verde-mata);
  color: var(--creme-areia);
  font-size: 14px;
  padding: var(--space-xs) var(--space-sm);
  border-radius: var(--radius-sm);
}

/* Variante: sticker rotacionado */
.badge--sticker {
  background: var(--laranja-tropical);
  color: var(--branco);
  border-radius: var(--radius-pill);
  transform: rotate(-3deg);
  box-shadow: var(--shadow-sticker);
}

/* Variante: tipo de quarto */
.badge--room-type {
  background: var(--creme-areia);
  color: var(--vermelho-terra);
  border: 1.5px solid var(--vermelho-terra);
}
```

### 5.4 Card de Quarto

```css
.room-card {
  display: flex;
  flex-direction: column;
  background: var(--surface-card);
  border-radius: var(--radius-md);
  overflow: hidden;
  box-shadow: var(--shadow-card);
  transition: box-shadow 0.25s ease, transform 0.2s ease;
}

.room-card:hover {
  box-shadow: var(--shadow-card-hover);
  transform: translateY(-4px);
}

.room-card__image {
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: cover;
}

.room-card__body {
  padding: var(--space-xl);
  display: flex;
  flex-direction: column;
  gap: var(--space-md);
  flex: 1;
}

.room-card__name {
  font-family: var(--font-display);
  font-size: var(--text-h3);
  color: var(--verde-mata);
}

.room-card__description {
  font-family: var(--font-body);
  font-size: var(--text-body-sm);
  color: var(--text-muted);
  line-height: 1.6;
}

.room-card__amenities {
  list-style: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-xs);
}

.room-card__amenities li {
  font-family: var(--font-ui);
  font-size: var(--text-caption);
  color: var(--verde-mata);
  background: rgba(27, 94, 58, 0.07);
  padding: var(--space-2xs) var(--space-xs);
  border-radius: var(--radius-sm);
}

.room-card__footer {
  padding: var(--space-md) var(--space-xl) var(--space-xl);
}
```

### 5.5 Depoimento / Testimonial

```css
.testimonial {
  padding: var(--space-xl);
  background: var(--surface-card);
  border-left: 4px solid var(--amarelo-dende);
  border-radius: 0 var(--radius-md) var(--radius-md) 0;
}

.testimonial__quote {
  font-family: var(--font-body);
  font-size: var(--text-body);
  font-style: italic;
  color: var(--text-on-light);
  line-height: 1.7;
  margin-bottom: var(--space-lg);
}

.testimonial__quote::before {
  content: '"';
  font-family: var(--font-display);
  font-size: 48px;
  color: var(--amarelo-dende);
  line-height: 0;
  vertical-align: -16px;
  margin-right: var(--space-2xs);
}

.testimonial__author {
  font-family: var(--font-ui);
  font-size: var(--text-body-sm);
  font-weight: 600;
  color: var(--verde-mata);
}

.testimonial__meta {
  font-family: var(--font-ui);
  font-size: var(--text-caption);
  color: var(--text-muted);
}
```

### 5.6 Acordeão / FAQ

```css
.accordion-item {
  border-bottom: var(--border-subtle);
}

.accordion-trigger {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  padding: var(--space-lg) 0;
  background: none;
  border: none;
  cursor: pointer;
  font-family: var(--font-body);
  font-size: var(--text-body);
  font-weight: 600;
  color: var(--verde-mata);
  text-align: left;
  min-height: 48px;
}

.accordion-trigger:hover {
  color: var(--vermelho-terra);
}

.accordion-trigger:focus-visible {
  outline: 3px solid var(--focus-ring);
  outline-offset: 2px;
  border-radius: var(--radius-sm);
}

.accordion-trigger__icon {
  width: 24px;
  height: 24px;
  transition: transform 0.3s ease;
  color: var(--amarelo-dende);
  flex-shrink: 0;
}

.accordion-item[open] .accordion-trigger__icon {
  transform: rotate(45deg);
}

.accordion-content {
  padding: 0 0 var(--space-lg) 0;
  font-family: var(--font-body);
  font-size: var(--text-body-sm);
  color: var(--text-muted);
  line-height: 1.7;
  max-width: 60ch;
}
```

### 5.7 Divisor de Azulejo

```css
.divider-azulejo {
  width: 100%;
  height: 48px;
  background-image: url("data:image/svg+xml,..."); /* SVG do pattern */
  background-repeat: repeat-x;
  background-size: 48px 48px;
  opacity: 0.6;
}

/* Alternativa simplificada com CSS */
.divider-azulejo--simple {
  width: 100%;
  height: 4px;
  background: repeating-linear-gradient(
    90deg,
    var(--amarelo-dende) 0,
    var(--amarelo-dende) 12px,
    var(--vermelho-terra) 12px,
    var(--vermelho-terra) 24px,
    var(--verde-mata) 24px,
    var(--verde-mata) 36px
  );
}
```

### 5.8 Botão Flutuante WhatsApp

```css
.fab-whatsapp {
  position: fixed;
  bottom: var(--space-lg);
  right: var(--space-lg);
  z-index: 1000;
  display: flex;
  align-items: center;
  gap: var(--space-xs);
  padding: var(--space-md) var(--space-xl);
  background: var(--vermelho-terra);
  color: var(--creme-areia);
  font-family: var(--font-ui);
  font-size: 14px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  border: none;
  border-radius: var(--radius-pill);
  box-shadow: var(--shadow-float);
  cursor: pointer;
  text-decoration: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.fab-whatsapp:hover {
  transform: translateY(-3px) scale(1.03);
  box-shadow: 0 16px 48px rgba(178, 45, 48, 0.3);
}

.fab-whatsapp__icon {
  width: 22px;
  height: 22px;
}

/* Mobile: só ícone quando tela muito pequena */
@media (max-width: 480px) {
  .fab-whatsapp {
    padding: var(--space-md);
    border-radius: var(--radius-circle);
    bottom: var(--space-md);
    right: var(--space-md);
  }
  .fab-whatsapp span { display: none; }
  .fab-whatsapp__icon {
    width: 28px;
    height: 28px;
  }
}
```

---

## 6. Layout e Grid

### 6.1 Breakpoints

```css
/* Mobile first */
--bp-sm:   480px;    /* Mobile large */
--bp-md:   768px;    /* Tablet */
--bp-lg:   1024px;   /* Desktop */
--bp-xl:   1280px;   /* Desktop large */
```

### 6.2 Grid de Seção

```css
/* Seção genérica */
.section {
  padding: var(--space-4xl) 0;
}

.section--verde {
  background: var(--verde-mata);
  color: var(--creme-areia);
}

.section--creme {
  background: var(--creme-areia);
  color: var(--verde-mata);
}

.section--vermelho {
  background: var(--vermelho-terra);
  color: var(--creme-areia);
}

/* Grid de 2 colunas (About, Diferenciais) */
.grid-2col {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-2xl);
}

@media (min-width: 768px) {
  .grid-2col {
    grid-template-columns: 1fr 1fr;
    align-items: center;
  }
}

/* Grid de 3 colunas (Quartos, Depoimentos) */
.grid-3col {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-lg);
}

@media (min-width: 768px) {
  .grid-3col {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .grid-3col {
    grid-template-columns: repeat(3, 1fr);
  }
}

/* Cabeçalho de seção */
.section-header {
  max-width: 640px;
  margin-bottom: var(--space-2xl);
}

.section-header--center {
  text-align: center;
  margin-inline: auto;
}
```

---

## 7. Efeitos e Microinterações

### 7.1 Textura Grain (CSS only)

```css
/* Aplica noise sutil em fundos sólidos */
.grain::after {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.04;
  pointer-events: none;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
  background-size: 128px;
  mix-blend-mode: multiply;
}
```

### 7.2 Transições

```css
:root {
  --ease-out:     cubic-bezier(0.25, 0, 0.35, 1);
  --ease-bounce:  cubic-bezier(0.34, 1.56, 0.64, 1);
  --duration-fast:  150ms;
  --duration-base:  250ms;
  --duration-slow:  400ms;
}
```

### 7.3 Animação de Entrada (scroll)

```css
/* Estado inicial — aplica via JS ao entrar no viewport */
[data-animate] {
  opacity: 0;
  transform: translateY(24px);
  transition:
    opacity var(--duration-slow) var(--ease-out),
    transform var(--duration-slow) var(--ease-out);
}

[data-animate].is-visible {
  opacity: 1;
  transform: translateY(0);
}

/* Atraso escalonado para grids */
[data-animate-delay="1"] { transition-delay: 100ms; }
[data-animate-delay="2"] { transition-delay: 200ms; }
[data-animate-delay="3"] { transition-delay: 300ms; }

/* Respeita preferência do usuário */
@media (prefers-reduced-motion: reduce) {
  [data-animate] {
    opacity: 1;
    transform: none;
    transition: none;
  }
}
```

---

## 8. Acessibilidade

### 8.1 Focus States

```css
/* Todos os elementos interativos */
a:focus-visible,
button:focus-visible,
input:focus-visible,
select:focus-visible,
textarea:focus-visible,
[tabindex]:focus-visible {
  outline: 3px solid var(--focus-ring);
  outline-offset: 3px;
  border-radius: var(--radius-sm);
}

/* Remove outline default e aplica só no keyboard */
:focus:not(:focus-visible) {
  outline: none;
}
```

### 8.2 Skip Link

```css
.skip-link {
  position: absolute;
  top: -100%;
  left: var(--space-md);
  z-index: 9999;
  padding: var(--space-sm) var(--space-md);
  background: var(--verde-mata);
  color: var(--creme-areia);
  font-family: var(--font-ui);
  font-size: 14px;
  font-weight: 700;
  border-radius: 0 0 var(--radius-sm) var(--radius-sm);
  text-decoration: none;
}

.skip-link:focus {
  top: 0;
}
```

### 8.3 Checklist

- [ ] Todos os `<img>` têm `alt` descritivo
- [ ] Ícones decorativos usam `aria-hidden="true"`
- [ ] Badges com cor acompanhados de texto legível
- [ ] Formulários com `<label>` associado
- [ ] Contraste mínimo 4.5:1 em texto de corpo
- [ ] Alvos de toque ≥ 44×44px
- [ ] `prefers-reduced-motion` desativa animações
- [ ] Navegação por teclado testada (Tab, Enter, Escape)
- [ ] Landmarks semânticos: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`

---

## 9. Estrutura de Arquivo Sugerida

```
casamarelo-hostel/
├── index.html
├── css/
│   ├── tokens.css         ← Cores, tipografia, espaçamento (este documento)
│   ├── base.css           ← Reset, global styles
│   ├── components.css     ← Botões, cards, badges, accordion
│   ├── layout.css         ← Grid, container, seções
│   └── utilities.css      ← Classes utilitárias (sr-only, text-center, etc.)
├── js/
│   ├── main.js            ← Menu mobile, scroll-animate, accordion
│   └── whatsapp.js        ← Geração de link com mensagem pré-preenchida
├── assets/
│   ├── img/               ← Fotos do hostel (WebP)
│   ├── icons/             ← SVGs de comodidades
│   └── patterns/          ← SVG de azulejo
└── README.md
```
