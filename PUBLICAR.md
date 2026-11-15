# Como publicar (passo a passo, ~10 minutos)

Este arquivo é só para a equipe. Pode apagar do repositório depois.

## 1. Criar o repositório
1. Entre em https://github.com/new com a conta da equipe (ou a sua).
2. Nome sugerido: `liastra-aic` · visibilidade **Public** (o Pages gratuito exige) · NÃO marque "Add a README".
3. Clique em **Create repository**.

## 2. Enviar os arquivos (sem usar terminal)
1. Na página do repositório vazio, clique em **uploading an existing file**.
2. Arraste TUDO que está na pasta `liastra-aic` (incluindo a pasta `vendor` e o arquivo oculto `.nojekyll`): `index.html`, `pt.html`, `README.md`, `.nojekyll`, `vendor/`.
3. Em **Commit changes**, confirme.

> Se preferir terminal, dentro da pasta: `git init -b main && git add . && git commit -m "Liastra Mission" && git remote add origin https://github.com/BabiDoo/NASA-Space-App-2026.git && git push -u origin main`

## 3. Ligar o GitHub Pages
1. **Settings → Pages**.
2. Em **Build and deployment → Source**, escolha **Deploy from a branch**.
3. Branch **main** e pasta **/(root)** → **Save**.
4. Em ~1 minuto o link aparece no topo: `https://babidoo.github.io/NASA-Space-App-2026/`.

## 4. Conferir
- Abra o link: a página inicial deve carregar e o botão de jogar abrir o simulador em 3D.
- Abra `…/pt.html` para a versão em português (para a submissão use o link principal, em inglês).
- Substitua `<github-user>/<repo>` no `README.md` pelo link real (ícone de lápis no GitHub).

## 5. Na submissão da NASA
Use o link principal (inglês). O desafio também pede o vídeo de 30 s em inglês e a página do projeto no portal da NASA, que dependem do time.
