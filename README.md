# Sprout Lost Dashboard · Spark Maxx Growth Ops

Dashboard estático single-file de análise de 193 deals lost (funil Sprout Social, 2026) e plano de retomada em 3 motivos prioritários: No-show · Ghosting em Solução · Adiou o projeto.

## Stack

Single-file HTML (~160 KB). Sem build step. Sem dependências de pacote.
Dependências externas via CDN:
- Chart.js 4 (gráficos)
- Google Fonts: Fraunces, Inter, JetBrains Mono

## Features

- Parte I (Diagnóstico) e Parte II (Plano de retomada) navegáveis por tabs na sidebar
- Modo claro / modo escuro com persistência em localStorage
- Mockups interativos de WhatsApp e e-mail (3 variações de copy por motivo)
- Trilha de 4 e-mails por motivo com explicação por trás de cada disparo
- Fluxograma visual com linha do tempo e branches por motivo
- Modo de edição inline: clica em qualquer texto, edita, baixa HTML editado

## Deploy no Vercel

### Opção 1 · CLI

```bash
npm i -g vercel
vercel login
vercel --prod
```

### Opção 2 · Conectar repo GitHub

1. `git init && git add . && git commit -m "first commit"`
2. Cria repo no GitHub e faz push
3. No Vercel: `Add new project` → importa o repo → deploy

### Opção 3 · Drag and drop

1. Acessa https://vercel.com/new
2. Arrasta a pasta deste projeto pra área de upload

Não há variáveis de ambiente. Não há build. Vercel detecta como projeto estático automaticamente.

## Desenvolvimento local

```bash
npx serve .
# ou
python3 -m http.server 8000
```

Abre `http://localhost:3000` (serve) ou `http://localhost:8000` (python).

## Estrutura

```
sprout-dashboard/
├── index.html       # Dashboard completo (single file)
├── vercel.json      # Headers + cache config
├── package.json     # Metadata
├── .gitignore
└── README.md
```

## Manutenção

Editar conteúdo do dashboard:
- Botão `✎ Modo edição` na sidebar do próprio dashboard
- Edita o texto direto na página
- Botão "⬇ Baixar HTML editado" gera nova versão com edições embutidas
- Substitui o `index.html` e re-deploya

## Domínio customizado

Após o primeiro deploy, no painel da Vercel:
`Project Settings → Domains → Add` e adiciona o domínio. Vercel gera os DNS records necessários.
