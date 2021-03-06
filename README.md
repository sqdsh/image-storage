# Image Storage
* По описанию проекта понятно что это хранилище фотографий для его владельца, который может поделиться доступом к сервису со своими соратниками
* Проект по работе напоминает хостинг картинок **[is-inside.me](https://is-inside.me/)**
* Frontend-часть проекта - HTML без каких-либо "особых" стилей. Сервис не задумывался как публичный, поэтому и смысла нет париться над его лицевой частью. **К тому-же всё было сделано за день.**

## Как запустить?
1. Установите библиотеки
2. Отредактируйте конфиг под себя
3. `node index.js`

### Важная информация относительно базы данных
1. При запуске проекта база данных создастся сама
2. Базой данных (`config.database.dialect`) может быть `mysql`, `mariadb`, `postgres` и `mssql`, но для этого нужно установить соответствующие библиотеки:
```bash
$ npm install --save pg pg-hstore # PostgreSQL
$ npm install --save mysql2 # Уже установлен
$ npm install --save mariadb
$ npm install --save sqlite3
$ npm install --save tedious # Microsoft SQL Server
```
3. Если требуется SQLite, в файле `index.js` **надо заменой с 31 по 35 строчку** вставить следующий код:
```js
const sequelize = new Sequelize({
    dialect: 'sqlite',
    storage: 'path/to/database.sqlite'
});
```

## Конфиг для ShareX
В проекте есть авто-генератор конфигурации для **ShareX**. Он доступен как по ссылке (`<URL сайта>/api/uploads/create`), так и в вашем аккаунте.
