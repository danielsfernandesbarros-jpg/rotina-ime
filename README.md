# Rotina IME

Rotina de estudos de 5h por dia para o IME, feita como app web instalável (PWA).
É HTML, CSS e JavaScript puros: não precisa instalar nada nem fazer build.

## Publicar pelo GitHub (uns 5 minutos)

1. Entre em github.com e crie um repositório novo (**New repository**). Nome sugerido: `rotina-ime`. Deixe como **Public**.
2. Na página do repositório, clique em **uploading an existing file** e envie **todos os arquivos desta pasta**. Extraia o `.zip` antes: envie os arquivos, não o `.zip`. Depois clique em **Commit changes**.
3. Vá em **Settings → Pages**. Em *Build and deployment*, escolha **Deploy from a branch**, branch **main**, pasta **/ (root)**, e salve.
4. Espere 1 ou 2 minutos. O endereço do app será `https://SEU-USUARIO.github.io/rotina-ime/`.

## Instalar no celular

- **Android (Chrome):** abra o endereço, toque no menu ⋮ e escolha **Instalar app** (ou **Adicionar à tela inicial**).
- **iPhone (Safari):** abra o endereço, toque em Compartilhar e escolha **Adicionar à Tela de Início**.

Depois de aberto uma vez com internet, o app também funciona offline.

## O que tem em cada arquivo

| Arquivo | Para quê |
| --- | --- |
| `index.html` | O app inteiro: telas, estilos e lógica (relógio, destaque "AGORA", abas) |
| `manifest.json` | Nome, cores e ícones do app instalado |
| `sw.js` | Faz o app funcionar offline |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` | Ícones do app |

## Como editar a rotina

Abra o `index.html` no GitHub (ícone de lápis), altere e clique em **Commit changes**.

- **Horários e textos:** cada linha da agenda é um `<div class="row ...">`. O horário mostrado fica em `<div class="time">` e o texto em `<div class="activity">`. Para o destaque "AGORA" acompanhar a mudança, ajuste também `data-start` e `data-end`, que são minutos desde 00:00 (por exemplo, 15:30 = 930).
- **Matérias de segunda a sexta:** dentro do `<script>`, no objeto `PLAN`.
- **Cores:** no começo do arquivo, na parte `:root`.

Para o celular pegar a versão nova, abra o app duas vezes. Se ainda mostrar a versão antiga, troque `rotina-ime-v1` por `rotina-ime-v2` no `sw.js`.

## Testar no computador (opcional)

Na pasta do projeto, rode `python3 -m http.server 8000` e abra `http://localhost:8000`.
