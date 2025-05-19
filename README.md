<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Insta Clone</title>
  <link rel="icon" href="screenshots/favicon-instaclone.png" type="image/png" />
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px auto;
      max-width: 800px;
      line-height: 1.6;
      color: #222;
    }
    h1, h2 {
      color: #333;
    }
    img {
      max-width: 100%;
    }
    .btn {
      display: inline-block;
      background: #333;
      color: #fff;
      padding: 10px 20px;
      margin: 20px 0;
      border-radius: 6px;
      text-decoration: none;
    }
    code {
      background: #f4f4f4;
      padding: 2px 6px;
      border-radius: 4px;
    }
    pre {
      background: #f4f4f4;
      padding: 10px;
      border-radius: 6px;
      overflow-x: auto;
    }
  </style>
</head>
<body>

  <div style="text-align:center;">
    <img src="screenshots/favicon-instaclone.png" alt="Insta Clone Logo" width="120" />
  </div>

  <h1>Insta Clone</h1>

  <p>Полноценный клон Instagram на React + Node.js + MongoDB.</p>

  <a class="btn" href="https://github.com/Dmitriy605-ss/insta-clone" target="_blank">Посмотреть код на GitHub</a>

  <h2>Возможности</h2>
  <ul>
    <li>Регистрация и вход</li>
    <li>Создание постов с фото</li>
    <li>Лайки и комментарии</li>
    <li>Настройка профиля</li>
    <li>Адаптивная мобильная версия</li>
  </ul>

  <h2>Стек</h2>
  <ul>
    <li>React / React Native</li>
    <li>TailwindCSS</li>
    <li>Node.js + Express</li>
    <li>MongoDB</li>
    <li>JWT авторизация</li>
  </ul>

  <h2>Скриншоты</h2>
  <p><strong>Главная:</strong></p>
  <img src="screenshots/home.png" alt="Главная страница" />
  <p><strong>Профиль:</strong></p>
  <img src="screenshots/profile.png" alt="Профиль" />

  <h2>Запуск</h2>
  <pre><code>git clone https://github.com/Dmitriy605-ss/insta-clone.git
cd insta-clone
npm install
npm run dev</code></pre>

  <h2>О проекте</h2>
  <p>
    Insta Clone — это учебный и демонстрационный проект, созданный для практики
    fullstack-разработки. Он повторяет ключевой функционал Instagram и может быть
    использован как основа для собственных соцсетей, блогов или галерей.
  </p>

  <h2>Планы</h2>
  <ul>
    <li>Push-уведомления</li>
    <li>Подписки и лента от друзей</li>
    <li>Сторис (временные посты)</li>
    <li>Подключение к облачному хранилищу (S3, Firebase)</li>
  </ul>

  <h2>Автор</h2>
  <p>
    Проект разработан <strong>Dmitriy605</strong><br/>
    <a href="https://github.com/Dmitriy605-ss" target="_blank">GitHub профайл</a>
  </p>

</body>
</html>
