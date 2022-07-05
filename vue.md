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
  Buefy использует набор иконок и шрифтов, если понадобится, их скачать отдельно: Material Design Icons CDN и Font Awesome 5 CDN.
  
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
  
