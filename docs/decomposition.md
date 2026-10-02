# Talking Travel

Декомпозиция обновлена: пользователь выбрал полную страницу Home Page на странице Get Started в Figma и первую страницу PDF вместо уменьшенной копии на Cover. Пользователь также заменил требование SCSS на обычный CSS и попросил выполнить всю страницу за один этап.

Исходный макет: https://www.figma.com/design/n1nSQGeq3fHzbsV6HGbBc8/Locofy-Sample-Project---Talking-Travel--Community-?node-id=1-2

```text
page
├── header
│   └── container
│       ├── logo
│       ├── desktop navigation
│       ├── mobile navigation (details / summary)
│       └── header actions
├── main
│   ├── hero
│   │   └── container
│   │       ├── h1
│   │       ├── description
│   │       └── links
│   ├── featured
│   │   └── container
│   │       ├── image
│   │       └── content (eyebrow, h2, description, link)
│   ├── destinations
│   │   └── container
│   │       ├── heading (eyebrow, h2)
│   │       └── list of four cards (image, h3, link)
│   ├── community
│   │   ├── heading (eyebrow, h2)
│   │   └── form
│   │       ├── heading (h3, description)
│   │       ├── destination input
│   │       ├── country select
│   │       ├── name input
│   │       ├── category select
│   │       ├── description textarea
│   │       └── submit button
│   └── stories
│       └── container
│           ├── heading (eyebrow, h2)
│           └── grid
│               ├── main story (image, h3, description, link)
│               └── three story cards (image, h3, description, link)
└── footer
    └── container
        ├── copyright
        └── navigation
```

Вёрстка: `index.html` и `css/style.css`. Все изображения и шрифты подключаются локально из `assets/travel` и `assets/fonts`. JavaScript и CSS-фреймворки не используются.

Контрольные ширины: 1280px, 768px и 360px. Исходный desktop-макет имеет ширину 1440px. Основной контейнер ограничен 1200px, контейнер hero и featured — 1160px.

Форма использует стандартные поля HTML и встроенную проверку обязательных полей. Серверной обработки нет: отправка возвращает на эту же страницу с введёнными значениями в адресной строке. Видеофайлы в материалах отсутствуют. Ссылки Story, Blog и блок о Швейцарии на главной открывают `story.html`; ссылки остальных историй ведут к существующим блокам главной.

## Hello Switzerland!

Декомпозиция дополнена по просьбе пользователя сверстать следующую, вторую страницу PDF. Структура главной сохранена; добавлена отдельная страница статьи. Остальные страницы PDF в этот этап не входят.

Исходный макет: https://www.figma.com/design/n1nSQGeq3fHzbsV6HGbBc8/Locofy-Sample-Project---Talking-Travel--Community-?node-id=41-10805

```text
story page
├── header (общие шапка и навигация)
├── main
│   ├── article
│   │   ├── opening
│   │   │   ├── header (eyebrow, h1, author)
│   │   │   └── figure (Matterhorn photo, lettering, decorative play icon)
│   │   ├── introduction (h2, paragraph)
│   │   ├── feature
│   │   │   ├── photo collage (three links to original photos)
│   │   │   └── content (blockquote, two paragraphs, gallery link)
│   │   ├── conclusion paragraph
│   │   ├── highlights (h2, three figures with captions)
│   │   └── aside (disclaimer)
│   └── community (общая форма)
└── footer (общий подвал)
```

Вёрстка статьи: `story.html` и `css/story.css`. Общие стили шапки, формы и подвала подключаются из `css/style.css`. Контейнер статьи ограничен 912px по Figma. На ширине 768px автор и фотоколлаж с текстом располагаются вертикально; на 360px галерея Highlights становится одноколоночной.

Новые изображения экспортированы из Figma в `assets/switzerland`; рукописная надпись экспортирована как SVG с контурами букв, чтобы не подменять отсутствующий шрифт. Курсивные варианты Roboto и Changa One добавлены в `assets/fonts`. Фотографии открываются по обычным ссылкам, кнопка View full gallery ведёт к Highlights. Значок воспроизведения на главном фото декоративный: без исходного видео воспроизведение не реализовано.
