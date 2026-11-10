# TabuadaQuest

Jogo educativo para praticar tabuada, com uma jornada organizada em 10 níveis.

É um aplicativo Android escrito em Java. O jogo em si é feito em HTML, CSS e JavaScript e roda localmente dentro de uma WebView, empacotado junto com o app.

## Tecnologias

- Java 17
- Android SDK 35 (funciona a partir do Android 6.0)
- WebView com conteúdo web local
- Gradle 8.9
- GitHub Actions para build e teste

## Como o projeto está organizado

| Pasta | O que tem |
| --- | --- |
| `app/` | Projeto Android: `MainActivity.java` e o manifesto |
| `ci/` | Conteúdo web do jogo, compactado em partes e remontado durante o build |
| `.github/workflows/` | Pipelines de build do APK e de smoke test |

## Build automatizado

Cada alteração enviada para a branch `main` dispara dois workflows no GitHub Actions:

- **Build Android APK**: remonta o conteúdo web, configura JDK 17 e Android SDK e gera o APK de debug.
- **Android Smoke Test**: valida se o aplicativo compila e abre corretamente.

O build também pode ser iniciado manualmente pela aba **Actions**.

## Como gerar o APK na sua máquina

Você precisa de JDK 17, Android SDK e Gradle 8.9. Os passos completos, incluindo a remontagem do conteúdo web, estão em `.github/workflows/build-apk.yml`. O comando final é:

```bash
gradle :app:assembleDebug
```

## O que aprendi com este projeto

- Empacotar uma aplicação web dentro de um app Android nativo.
- Montar um pipeline de build do zero no GitHub Actions.
- Versionar e validar cada entrega com teste automatizado.

---

## English

Educational game for practicing multiplication tables, organized as a 10-level journey.

It is an Android app written in Java. The game itself is built with HTML, CSS and JavaScript and runs locally inside a WebView, packaged with the app.

**Stack:** Java 17, Android SDK 35 (Android 6.0+), WebView, Gradle 8.9, GitHub Actions.

**CI:** every push to `main` runs a workflow that builds the debug APK and a smoke test that checks the app builds and starts.

---

Feito por [Alex Castro](https://github.com/alexfcastro)
