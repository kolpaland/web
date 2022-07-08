# Создание приложения Vue

Создаем простой одностраничный проект с помощью Vuejs и Buefy.
Чтобы использовать стили Buefy, следует установить Vue2.6+.

Пока поддержки Vue3 нет, но есть плагин Vue CLI 3.x, чтобы добавить Buefy в проект. Его пока не используем.

1. Установка Vue, инструкция взята из официальной [документации](https://v2.vuejs.org/v2/guide/installation.html).
Скачать можно [тут](https://v2.vuejs.org/js/vue.js). Отмечу, что это development версия, для production стоит взять минимизированную версию https://v2.vuejs.org/js/vue.min.js.
Просто добавить напрямую в html с помощью тэга <script>.
Добавим в папку modules проекта:
```
<script src="./modules/vue.js"></script>
```
Можно скачать стабильную версии с CDN: "https://cdn.jsdelivr.net/npm/vue@2.7.0/dist/vue.js".
  
  2. Создание приложения.
  ```
  //index.html
  <body>
    <div id="app">{{ message }}</div>
    <script src="./main.js"></script>
</body>  
  ```
  
  ```
  //main.js
  var app = new Vue({
    el: '#app',
    data: {
      message: 'Hello Vue!'
    }
  })  
  ```
  3. Установка стилей Buefy
  Инструкция по установке: https://buefy.org/documentation/start#standalone. 
    
  Для установки Buefy просто скачайте:
  
  * Скрипт [buefy.min.js](https://unpkg.com/buefy/dist/buefy.min.js)
  * Стили [buefy.min.css](https://unpkg.com/buefy/dist/buefy.min.css)
  
  Затем добавьте в разметку: 
  
  ```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="./styles/buefy.min.css">
</head>

<body>
    <div id="app">
        <!-- Buefy components goes here -->
    </div>

    <script src="./modules/vue.js"></script>
    <!-- Full bundle -->
    <script src="./modules/buefy.min.js"></script>

    <script>
        new Vue({
            el: '#app'
        })
    </script>
</body>
</html>
  ```
 Buefy использует набор иконок и шрифтов, их нужно скачать отдельно: Material Design Icons CDN и Font Awesome 5 CDN.
 К примеру, [Material Design Icons](https://cdn.jsdelivr.net/npm/@mdi/font@5.8.55/). 
 
 Понадобятся эти два файлика: 
 * [fonts/materialdesignicons-webfont.woff2](https://cdn.jsdelivr.net/npm/@mdi/font@5.8.55/fonts/materialdesignicons-webfont.woff2)
  * [css/materialdesignicons.min.css](https://cdn.jsdelivr.net/npm/@mdi/font@5.8.55/css/materialdesignicons.min.css)
  
  ```
  <link rel="stylesheet" href="./styles/materialdesignicons.min.css">
  ```
  Создать папку  fonts в корне проекта и там разместить *.woff2
  
  ## SPA
  
  Нам нужно одностраничное приложение, максимально похожее на десктопное.
  
  Описание взято [здесь](https://vueschool.io/courses/vue-router-4-for-everyone)
  
  Single Page Applications are web apps or sites that interact with the user by dynamically rewriting the current page rather than loading entire new pages from the server.

This approach allows us to only fetch the data/section of our page that is needed when a user interacts with our app. By dynamically rewriting smaller chunks of our site, it prevents us from re-downloading already loaded resources such as the images, scripts, CSS, etc.

As a result SPA’s tend to improve the user experience by:
  * Providing faster load times between page navigations
  * Behaving more like traditional desktop applications
  
  You need to know about the Vue Router to create rapid prototypes or ımpressive, full-blown Vue.js SPA’s.
  
  ## Pinia
  
  Pinia - это  библиотечка для хранения состояний компонентов, это позволяет обмениваться состояниями между компонентами и страницами (дочерними, родительскими, вне зависимости от родства).
 
  https://pinia.vuejs.org/introduction.html
  
  Pinia is a store library for Vue, it allows you to share a state across components/pages. If you are familiar with the Composition API, you might be thinking you can already share a global state with a simple export const state = reactive({}). This is true for single page applications but exposes your application to security vulnerabilities if it is server side rendered. But even in small single page applications, you get a lot from using Pinia:
* Devtools support
  - A timeline to track actions, mutations
  - Stores appear in components where they are used
  - Time travel and easier debugging
  
* Hot module replacement
  - Modify your stores without reloading your page
  - Keep any existing state while developing
  
* Plugins: extend Pinia features with plugins
* Proper TypeScript support or autocompletion for JS users
* Server Side Rendering Support
