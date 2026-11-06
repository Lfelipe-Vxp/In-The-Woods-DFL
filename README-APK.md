# In The Woods - gerar o APK para instalar no celular

Esta pasta e um projeto pronto para virar um app Android (APK).
O jogo esta em `www/index.html`. Arte, sons e fontes estao dentro desse arquivo, entao o app funciona sem internet.

Existem dois caminhos. O **Caminho A e o mais facil**: nao precisa instalar nada no computador.

---

## Caminho A - Gerar o APK na nuvem com o GitHub (sem Android Studio)

1. Crie uma conta gratuita em https://github.com
2. Clique em **New repository**, escolha um nome (ex.: `in-the-woods`) e escolha **Public** (para ter um link de download que qualquer pessoa abre) ou **Private** (so voce ve). Crie o repositorio.
3. Descompacte este zip no computador.
4. No repositorio, clique em **Add file > Upload files** e arraste **todo o conteudo** da pasta descompactada (inclusive a pasta `.github`). Clique em **Commit changes**.
   - A pasta `.github` e oculta em alguns sistemas. Se ela nao aparecer no seu computador, ative "mostrar arquivos ocultos". Se ainda assim nao subir, use **Add file > Create new file**, digite o nome `.github/workflows/gerar-apk.yml` e cole o conteudo do arquivo `github-workflow/gerar-apk.yml`.
5. Abra a aba **Actions**. Escolha **Gerar APK** e clique em **Run workflow** (se ele ja nao tiver comecado sozinho).
6. Espere de 5 a 15 minutos ate aparecer um visto verde.
7. **Download direto no celular:** na pagina principal do repositorio, abra **Releases** (coluna da direita no computador, ou aba/menu no celular). Toque na versao mais nova e em **In-The-Woods.apk** para baixar.
   - Se o repositorio for **publico**, qualquer pessoa baixa pelo link `https://github.com/SEU-USUARIO/SEU-REPOSITORIO/releases/latest/download/In-The-Woods.apk`.
   - Se for **privado**, so quem estiver logado na sua conta baixa. Para enviar a amigos, deixe o repositorio publico ou mande o APK por Google Drive.
   - Plano B: na execucao concluida (aba Actions), em **Artifacts**, baixe `in-the-woods-apk` (vem dentro de um zip).

Se a execucao falhar (X vermelho), clique nela, abra a etapa que falhou e copie as ultimas linhas do erro. Com isso da para corrigir.

---

## Caminho B - Gerar no computador com o Android Studio

Instale o **Node.js 22 ou mais novo** (https://nodejs.org) e o **Android Studio** (https://developer.android.com/studio). Depois, no terminal, dentro desta pasta:
```
npm run setup
npm run add-android
npm run icons
npm run sync
npm run open
```
No Android Studio: `Build > Build Bundle(s) / APK(s) > Build APK(s)`.
O arquivo fica em `android/app/build/outputs/apk/debug/app-debug.apk`.

---

## Instalar no celular
1. Passe o `In-The-Woods.apk` para o celular (cabo USB, Google Drive, WhatsApp para voce mesmo, etc.).
2. Abra o arquivo. O Android vai pedir para permitir **instalar apps desconhecidos** para o app que voce usou para abrir (Arquivos, Chrome...). Permita.
3. Se o Play Protect avisar, escolha **Instalar mesmo assim**. E normal para apps de fora da loja.
4. Abra **In The Woods** pelo icone. O jogo abre em tela cheia, na horizontal.

O APK gerado e de teste ("debug"): funciona normalmente para jogar e compartilhar. Se um dia mandar uma atualizacao, o celular aceita instalar por cima desde que seja gerado pelo mesmo caminho/chave.

## Atualizar o jogo
Troque `www/index.html` pela versao nova e gere o APK de novo.

## Licencas
- Fonte Metal Mania: licenca livre SIL OFL (copia em `licenses/`).
- Fonte "The Gonjuring": o arquivo nao veio com licenca. Para uso pessoal e entre amigos nao ha problema; se um dia for publicar ou vender, confirme a licenca com a fonte de onde baixou.

---

## Caminho C - So com o celular (sem computador)

1. Baixe o `in-the-woods-android.zip` no celular (nao precisa descompactar).
2. Entre em https://github.com pelo navegador do celular e crie uma conta gratuita.
3. Crie um repositorio novo (https://github.com/new): escolha um nome, marque **Public** e marque **Add a README file**.
4. No repositorio: **Add file > Upload files**, escolha o `in-the-woods-android.zip` (em Downloads) e toque em **Commit changes**.
5. Ainda no repositorio: **Add file > Create new file**. No campo do nome digite `.github/workflows/gerar-apk.yml` (as barras criam as pastas). Cole o conteudo do arquivo `github-workflow/gerar-apk-celular.yml` (ele esta neste zip e tambem foi enviado na conversa). Toque em **Commit changes**.
6. Abra a aba **Actions**. O fluxo "Gerar APK" comeca sozinho. Espere de 5 a 15 minutos ate o visto verde.
7. Abra **Releases** (https://github.com/SEU-USUARIO/SEU-REPOSITORIO/releases), toque em **In-The-Woods.apk** e instale.
