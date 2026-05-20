# Prompt para Claude Code · Deploy do Sprout Lost Dashboard na Vercel

Copia e cola tudo abaixo no Claude Code:

---

```
Preciso fazer o deploy de um dashboard HTML estático na Vercel.

CONTEXTO
O projeto é um dashboard single-file de análise de leads perdidos e plano de
retomada (Spark Maxx · Sprout Social). É HTML puro com Chart.js via CDN.
Sem build step. Sem dependências de pacote.

ARQUIVOS DO PROJETO
- index.html (~160 KB) — dashboard completo
- vercel.json — headers de segurança + cache control
- package.json — metadata mínimo
- .gitignore
- README.md

TAREFAS
1. Cria a pasta `sprout-dashboard/` na minha máquina local com os arquivos
   que vou anexar
2. Inicializa um repositório git nessa pasta
3. Roda `vercel --prod` pra subir direto no projeto (já tenho a CLI da Vercel
   instalada e estou logado)
4. Me retorna a URL de produção gerada
5. Configura cache invalidation: o index.html deve ter no-cache pra eu poder
   atualizar sem aguardar TTL (já está no vercel.json mas confirma)
6. Opcional: se eu quiser conectar um domínio customizado depois, me explica
   o caminho pelo painel

VALIDAÇÃO PÓS-DEPLOY
- Acessa a URL gerada e confere que:
  · Carrega o dashboard com sidebar à esquerda
  · O toggle Claro/Escuro funciona
  · Os charts renderizam (Chart.js do CDN cdnjs.cloudflare.com)
  · As tabs Parte I / Parte II alternam
  · Os mockups de WhatsApp aparecem com fundo verde e bolhas
  · As tabs E1/E2/E3/E4 dos e-mails ficam HORIZONTAIS em grid de 4 colunas
    (importante: já tive problema com elas ficando verticais — confirma)

OBSERVAÇÕES
- Não preciso de variáveis de ambiente
- Não preciso de build script
- O projeto funciona standalone abrindo o index.html no navegador
- Se a CLI da Vercel não estiver instalada, instala com `npm i -g vercel` antes
- O vercel.json já tem cleanUrls=true e headers de segurança configurados

UPDATES FUTUROS
Quando eu precisar atualizar o conteúdo, vou:
1. Editar o index.html localmente (ou baixar versão editada via botão "Modo
   edição" do dashboard)
2. Rodar `vercel --prod` de novo
Confirma que esse fluxo está correto e me ensina o atalho se houver.
```

---

## Como entregar os arquivos pro Claude Code

**Opção 1 · ZIP (mais simples):**
Anexa o arquivo `sprout-dashboard.zip` na mesma mensagem do prompt acima.
Claude Code vai descompactar e seguir as instruções.

**Opção 2 · Arquivos individuais:**
Anexa os 5 arquivos separadamente:
- `index.html`
- `vercel.json`
- `package.json`
- `.gitignore`
- `README.md`

**Opção 3 · Direto do Claude Code se estiver na pasta:**
Se já tem a pasta local, abre o Claude Code dentro dela e cola só esse trecho:

```
Faz deploy desse projeto estático na Vercel.
Roda `vercel --prod` e me devolve a URL.
```
