# Onyx — Painel

Painel de cliente para gestão de bots WhatsApp e créditos. Site estático puro (HTML/CSS/JS, sem build).

## Estrutura

```
onyx-site/
├── index.html          → redireciona pra html/index.html (abra este pra testar)
├── html/
│   └── index.html      → a página do painel
├── css/
│   ├── variables.css   → paleta de cores, fontes, tokens de design
│   ├── base.css        → reset e estilos globais
│   ├── layout.css       → sidebar, topbar, grid principal
│   ├── components.css  → cards, botões, pills, status
│   └── responsive.css  → regras de mobile/tablet
└── js/
    ├── data.js          → camada de dados (mock). Troque pelas chamadas reais de API aqui
    ├── render.js        → funções que transformam dados em HTML
    └── app.js            → controlador: busca dados, popula a tela, liga interações
```

## Como rodar

Abra `index.html` direto no navegador, ou suba um servidor local (recomendado, pra evitar bloqueios de CORS no futuro):

```bash
cd onyx-site
python3 -m http.server 8000
```

Depois acesse `http://localhost:8000`.

## Plugando numa API de verdade

Toda a "mentira" do protótipo está em `js/data.js`. As quatro funções (`fetchAccount`, `fetchStats`,
`fetchBots`, `fetchActivity`) retornam dados fake via `Promise`. Pra conectar no backend de verdade,
troque o corpo de cada uma por um `fetch('https://sua-api.com/...')`, mantendo o mesmo formato de
retorno (mesmos campos), e o resto do site continua funcionando sem mudar nada.

## Próximos passos sugeridos

- Tela de conexão de bot via QR Code
- Página de planos e recarga via PIX
- Catálogo de endpoints com playground
- Autenticação (login/sessão)
