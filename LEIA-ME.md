# Meu treino: projeto para gerar o app

O app inteiro está em `www/index.html`. Você pode editar o treino, a dieta e as
ideias de refeição direto nesse arquivo, mas normalmente não precisa: o app já
gera tudo sozinho a partir do cadastro (altura, peso, objetivo, etc).

## Para vender na Google Play

Siga `store/RELEASE.md` para gerar o `.aab` assinado (é o formato que a Play
Store exige). A pasta `store/` também tem:
- `politica-de-privacidade.html`: publique em algum link público e cole na
  ficha do app no Play Console.
- `ficha-da-loja.md`: rascunho pronto de nome, descrição e categoria.
- `aviso-legal.md`: pontos práticos a revisar antes de cobrar pelo app.

## Opção A: gerar o APK de teste online, sem instalar nada (GitHub)

1. Crie uma conta gratuita em github.com e um repositório novo (pode ser privado).
2. Envie todo o conteúdo desta pasta para o repositório (botão "Add file > Upload files").
   Envie também a pasta `.github`; se ela estiver oculta no seu computador, ative "mostrar arquivos ocultos".
3. No repositório, abra a aba **Actions**, escolha **Gerar APK** e toque em **Run workflow**.
4. Espere uns 5 minutos. Abra a execução concluída e baixe **meu-treino-apk** em "Artifacts".
5. Descompacte o arquivo baixado: dentro está o `app-debug.apk`.

## Opção B: gerar no computador (Android Studio)

Requisitos: Node.js 18+ e Android Studio instalados.

```
npm install
npx cap add android
npx cap sync android
npx cap open android
```

No Android Studio: **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
O arquivo fica em `android/app/build/outputs/apk/debug/app-debug.apk`.

## Instalando no celular

1. Envie o `app-debug.apk` para o celular (WhatsApp, e-mail, Drive, cabo).
2. Abra o arquivo. Se o Android pedir, permita "instalar apps de fontes desconhecidas".
3. Instale e abra o app "Meu treino".

## Observações

- Suas cargas e marcações ficam salvas no próprio app. Se desinstalar, elas se perdem;
  use o botão **Backup** dentro do app para guardar o treino.
- Os vídeos precisam de internet.
- É um APK de teste (debug): funciona normalmente, só não serve para publicar na Play Store.
