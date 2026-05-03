# Convenções

> Último mapeamento: 2026-05-02

## Estilo de Código

### HTML
- Indentação com **2 espaços**
- Atributos HTML com aspas duplas
- Uso de HTML5 semântico: `<main>`, `<section>`, `<nav>`, `<article>`, `<footer>`
- Atributos `aria-label` presentes em todos os links e botões de ação
- Tags auto-fechantes com barra final (`<img ... />`, `<meta ... />`)

### CSS
- **Custom Properties** como design tokens — todas definidas em `:root`
- Comentários com `/* */` para separar seções (ex: `/* Profile Section */`, `/* Footer */`)
- Seletores simples, sem BEM, sem nesting (CSS puro)
- Media queries no final do bloco de estilos
- Transições com `cubic-bezier` customizados para efeitos premium
- `backdrop-filter` para glassmorphism com prefixo `-webkit-` como fallback

### JavaScript
- Funções declaradas com `function` (não arrow functions no nível raíz)
- Template literals para strings multilinhas (vCard)
- `const` / `let` (sem `var`)
- Event listeners via `addEventListener` (não inline `onclick` — exceto uma exceção no `.featured-service`)
- `requestAnimationFrame` para animações de performance

## Padrões de Design

### Glassmorphism
- Background semitransparente (`rgba(255,255,255,0.05)`)
- Borda sutil (`rgba(255,255,255,0.1)`)
- `backdrop-filter: blur(16px)` no card principal
- `box-shadow` com múltiplas camadas + `inset` highlight

### Responsividade
- Mobile-first (card com `max-width: 420px`)
- Uma única media query `@media (max-width: 400px)` para ajustes finos
- `window.matchMedia("(hover: hover)")` para desabilitar tilt 3D em touch

### Micro-interações
- Efeito **ripple** nos botões (span criado dinamicamente)
- **Tilt 3D** do card seguindo o mouse (com `requestAnimationFrame`)
- Hover com `translateY` e `scale` nos action buttons
- Shimmer/sweep no botão CTA (`::before` com `linear-gradient`)

## Tratamento de Erros

- **Não há tratamento de erros explícito.** Nenhum `try/catch`.
- A função `downloadVCard` assume que `Blob` e `URL.createObjectURL` estão disponíveis (compatibilidade ampla, mas sem fallback).
- Limpeza de recursos no vCard usa `setTimeout` de 100ms para remover o elemento `<a>` e revogar o Object URL.

## Acessibilidade

- `aria-label` em todos os botões de ação e links sociais ✅
- `alt` text nas imagens ✅
- `lang="pt-BR"` no `<html>` ✅
- Sem `role` explícito no card principal (poderia ser `role="main"` ou usar `<main>` — já usa `<main>`) ✅
- **Faltando:** `rel="noopener"` presente nos links externos ✅, mas falta `aria-live` ou `role="status"` para feedback de ações.
