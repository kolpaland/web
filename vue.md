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
Можно скачать стабильную версии с CDN: "https://cdn.jsdelivr.net/npm/vue@2.7.0/dist/vue.js"
