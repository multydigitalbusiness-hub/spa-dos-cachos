# Arquitetura

> Último mapeamento: 2026-05-02

## Padrão Arquitetural

**Arquivo único estático (Single-File Architecture)**

Todo o projeto reside em um único `index.html` contendo HTML, CSS e JavaScript inline. Não há separação de arquivos, módulos ou componentes. Trata-se de um cartão digital de negócios (digital business card) para a empresa **ITEC — Assistência Técnica**.

## Camadas

```
┌─────────────────────────────────┐
│        Apresentação (HTML)       │  Estrutura semântica, layout
├─────────────────────────────────┤
│         Estilo (CSS inline)      │  Design system via custom properties
├─────────────────────────────────┤
│     Interatividade (JS inline)   │  Ripple, tilt 3D, vCard download
└─────────────────────────────────┘
```

Não há camada de dados, backend ou API.

## Fluxo de Dados

1. **Carregamento** → navegador faz parse do HTML, carrega fontes/ícones via CDN
2. **Renderização** → CSS aplica glassmorphism, animação fadeIn no card principal
3. **Interação do usuário** → JS escuta eventos:
   - `mousedown` em botões → efeito ripple
   - `mousemove` no documento → tilt 3D do card (apenas em dispositivos com hover)
   - Click em "Salvar Contato" → gera Blob vCard e dispara download
4. **Saídas externas** → links abrem WhatsApp, Google Maps, Instagram, Google Review

## Abstrações

| Abstração | Implementação |
|-----------|---------------|
| Design tokens | CSS Custom Properties (`:root`) |
| Card glassmorphism | Classe `.glass-card` com `backdrop-filter` |
| Botões de ação | Grid `.action-grid` com `.action-btn` |
| Efeito ripple | Função `createRipple()` |
| Tilt 3D | `requestAnimationFrame` + `perspective/rotateX/rotateY` |

## Pontos de Entrada

- **`index.html`** — único ponto de entrada. Abre direto no navegador.
- Nenhum roteamento — é uma SPA de página única sem framework.

## Diagrama de Componentes Visuais

```
index.html
├── .bg-container + .bg-overlay     → Fundo com blur
├── .glass-card (main)              → Container principal
│   ├── .profile                    → Logo, nome, subtítulo, descrição
│   ├── .cta-btn                    → Botão principal (Google Review)
│   ├── .action-grid                → Grid 2×2 de ações
│   │   ├── WhatsApp
│   │   ├── Salvar Contato
│   │   ├── Ligar Agora
│   │   └── Localização
│   ├── .featured-service           → Card de serviço destacado
│   └── .footer                     → Instagram + copyright + crédito dev
└── <script>                        → Year, vCard, ripple, tilt 3D
```
