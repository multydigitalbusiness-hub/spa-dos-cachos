# Testes

> Último mapeamento: 2026-05-02

## Situação Atual

**Nenhum framework de testes configurado.** O projeto não possui:

- Testes unitários
- Testes de integração
- Testes end-to-end (E2E)
- Testes de acessibilidade automatizados
- CI/CD pipeline

## Recomendações

Para um projeto deste porte (cartão digital estático), uma suíte completa de testes pode ser excessiva. No entanto, os seguintes testes seriam valiosos:

### Testes Visuais / Manuais
- [ ] Verificar renderização em Chrome, Firefox, Safari (mobile e desktop)
- [ ] Verificar que `backdrop-filter` funciona ou degrada graciosamente
- [ ] Testar download do vCard em iOS e Android
- [ ] Confirmar que links do WhatsApp abrem o app correto
- [ ] Verificar responsividade em telas < 400px

### Testes Automatizados Sugeridos
- **Lighthouse CI** — auditar performance, acessibilidade, SEO, boas práticas
- **HTML Validator** (W3C) — validar markup
- **Playwright/Puppeteer** — testar download do vCard e navegação de links
- **axe-core** — auditoria de acessibilidade automatizada

### Cobertura de Funcionalidades

| Funcionalidade | Testável? | Método sugerido |
|----------------|-----------|-----------------|
| Download vCard | Sim | E2E (Playwright) — verificar que blob é criado |
| Efeito ripple | Sim | E2E — simular click e verificar `.click-ripple` |
| Tilt 3D | Sim | E2E — verificar `transform` no mousemove |
| Links externos | Sim | E2E — verificar `href` e `target="_blank"` |
| Responsividade | Sim | Lighthouse / Chrome DevTools |
| Fontes carregadas | Sim | Performance audit |

## Validação Manual Realizada

- Estrutura HTML verificada: semântica correta com `<main>`, `<section>`, `<nav>`, `<article>`, `<footer>`
- Atributos de acessibilidade presentes (`aria-label`, `alt`)
- Links verificados manualmente (URLs formatadas corretamente)
