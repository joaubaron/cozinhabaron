# Cozinha Baron

PWA de landing page para o blog [Cozinha Baron](https://cozinhabaron.blogspot.com/search/label/Jantar%20a%20dois) — receitas caseiras com sabor.

## 📁 Estrutura

```
cozinhabaron/
├── index.html        # Landing page principal
├── manifest.json     # Configuração PWA
├── sw.js             # Service Worker com cache automático
├── logo.png          # Logo exibida no anel animado
├── icon-192.png      # Ícone PWA 192x192
├── icon-512.png      # Ícone PWA 512x512
└── .github/
    └── workflows/
        └── deploy.yml  # Deploy automático para GitHub Pages
```

## 🚀 Deploy

O deploy é feito automaticamente via **GitHub Actions** a cada push na branch `main`.

O workflow:
1. Atualiza o `CACHE_VERSION` no `sw.js` com a data e hora atual (fuso de São Paulo)
2. Commita o `sw.js` atualizado no repositório
3. Publica os arquivos no GitHub Pages

## ⚙️ Service Worker

O `sw.js` faz cache dos assets principais para funcionamento offline. A versão do cache é atualizada automaticamente a cada deploy, garantindo que os usuários sempre recebam a versão mais recente.

```js
const CACHE_VERSION = '22.04.2026-1047'; // atualizado automaticamente
const CACHE_NAME = `cozinha-baron-${CACHE_VERSION}`;
```

## 📱 PWA

O site pode ser instalado como app em dispositivos móveis e desktop. Configurações no `manifest.json`:

- **Tema:** `#c45e3c` (terra)
- **Fundo:** `#f5ede3` (creme)
- **Orientação:** portrait
- **Display:** standalone

## 🌐 Acesso

- **Site:** `https://joaubaron.github.io/cozinhabaron/`
- **Blog:** [Cozinha Baron no Blogger](https://cozinhabaron.blogspot.com/search/label/Jantar%20a%20dois)
