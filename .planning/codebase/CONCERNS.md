# Preocupações

> Último mapeamento: 2026-05-02

## 🔴 Alta Prioridade

### Imagens ausentes no repositório

- **Arquivos faltando:** `profile.png`, `background.png`, `service.png`
- **Impacto:** A página renderiza com imagens quebradas sem esses arquivos
- **Localização:** `index.html` linhas 69, 495, 564
- **Ação:** Adicionar as imagens ao repositório ou atualizar os caminhos

### Nome do diretório inconsistente

- **Problema:** O diretório se chama `spaDosCachos` (sugere salão de beleza) mas contém o cartão digital da **ITEC Assistência Técnica** (reparo de celulares)
- **Impacto:** Confusão na organização do workspace
- **Ação:** Renomear para algo como `itec-digital-card`

## 🟡 Média Prioridade

### Inline `onclick` no featured-service

- **Localização:** `index.html` linha 559
- **Problema:** `onclick="window.open(...)"` inline viola o padrão do resto do código (que usa `addEventListener`)
- **Impacto:** Inconsistência de estilo + potencial bloqueio por pop-up blockers
- **Ação:** Migrar para `addEventListener` consistente

### Sem fallback para Font Awesome

- **Problema:** Se o CDN do Font Awesome falhar, todos os ícones desaparecem sem texto alternativo
- **Localização:** `index.html` linha 24–27
- **Impacto:** Interface fica sem ícones — botões ficam com apenas o texto
- **Ação:** Considerar ícones SVG inline para os críticos (WhatsApp, telefone)

### Open Graph image usa caminho relativo

- **Localização:** `index.html` linha 12
- **Problema:** `<meta property="og:image" content="profile.png" />` — deveria ser URL absoluta para funcionar em compartilhamentos de redes sociais
- **Ação:** Atualizar para URL absoluta quando deployado

### Meta tag `og:url` ausente

- **Localização:** `index.html` — seção `<head>`
- **Problema:** Falta `<meta property="og:url">` para SEO social
- **Ação:** Adicionar com URL canônica do deploy

## 🟢 Baixa Prioridade

### Performance — Carregamento de font-weight desnecessários

- **Problema:** Carrega Montserrat com pesos 300, 400, 500, 600, 700 — mas o código usa apenas 400, 500, 600 e 700
- **Localização:** `index.html` linha 20
- **Ação:** Remover peso 300 do import do Google Fonts

### Sem favicon

- **Problema:** Nenhum `<link rel="icon">` definido
- **Impacto:** Navegador exibe ícone padrão na aba
- **Ação:** Adicionar favicon da ITEC

### CSS não minificado

- **Problema:** ~450 linhas de CSS inline sem minificação
- **Impacto:** Desprezível neste tamanho (~19 KB total), mas aumento desnecessário do payload
- **Ação:** Opcional — considerar minificação se performance for prioridade

### vCard com dados limitados

- **Localização:** `index.html` linhas 601–607
- **Problema:** vCard não inclui endereço físico, email ou foto — campos úteis para um cartão de contato completo
- **Ação:** Enriquecer dados do vCard com informações adicionais disponíveis

## Segurança

- ✅ `rel="noopener"` em todos os links `target="_blank"`
- ✅ Sem formulários, sem input de usuário, sem backend
- ✅ Sem cookies, sem localStorage, sem dados sensíveis
- ⚠️ Número de telefone exposto em texto claro (esperado para cartão comercial)
- **Risco geral: Muito baixo** — site puramente estático sem interação com dados do usuário

## Dívida Técnica

| Item | Severidade | Esforço |
|------|-----------|---------|
| Adicionar imagens ausentes | Alta | Baixo |
| Renomear diretório | Alta | Baixo |
| Corrigir OG image path | Média | Baixo |
| Adicionar favicon | Baixa | Baixo |
| Migrar onclick inline | Média | Baixo |
| Enriquecer vCard | Baixa | Baixo |
| Otimizar font weights | Baixa | Baixo |
