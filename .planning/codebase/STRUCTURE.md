# Estrutura

> Último mapeamento: 2026-05-02

## Layout do Diretório

```
spaDosCachos/
├── index.html          (19.4 KB)  — Aplicação completa (HTML + CSS + JS)
├── logoMulty.webp      (178 KB)   — Logo da desenvolvedora "Multy Digital"
├── profile.png         (ausente)  — Imagem de perfil/logo da ITEC
├── background.png      (ausente)  — Imagem de fundo do card
├── service.png         (ausente)  — Imagem do serviço destacado
└── .planning/                     — Documentação do mapeamento (gerado)
    └── codebase/
        └── *.md
```

## Localizações-Chave

| O quê | Onde |
|-------|------|
| Estrutura HTML | `index.html` linhas 1–484 (head) e 485–673 (body) |
| CSS Custom Properties | `index.html` linhas 30–39 |
| Estilos do card | `index.html` linhas 89–127 |
| Grid de ações | `index.html` linhas 205–267 |
| Botão CTA | `index.html` linhas 269–321 |
| Seção de serviço | `index.html` linhas 323–404 |
| Footer e créditos | `index.html` linhas 406–461 |
| Responsividade | `index.html` linhas 464–468 |
| JavaScript (lógica) | `index.html` linhas 595–671 |
| Função vCard | `index.html` linhas 600–620 |
| Efeito ripple | `index.html` linhas 623–642 |
| Tilt 3D | `index.html` linhas 644–670 |

## Convenções de Nomenclatura

- **Classes CSS:** kebab-case (ex: `glass-card`, `action-btn`, `btn-whatsapp`)
- **IDs:** camelCase (ex: `card3d`, `year`)
- **Funções JS:** camelCase (ex: `downloadVCard`, `createRipple`)
- **Arquivos de imagem:** camelCase ou simples (ex: `logoMulty.webp`, `profile.png`)

## Observações sobre a Estrutura

1. **Nome do diretório não corresponde ao conteúdo:** O diretório se chama `spaDosCachos` (sugere um salão/spa de cabelos cacheados), mas o conteúdo é o cartão digital da **ITEC Assistência Técnica**. Pode ser um diretório temporário ou reutilizado.
2. **Arquivos de imagem ausentes:** 3 de 4 imagens referenciadas no HTML não estão presentes no repositório.
3. **Sem separação de arquivos:** CSS e JS são inline — não há `style.css` ou `script.js` separados.
