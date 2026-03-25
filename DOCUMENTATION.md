# Полная документация проекта Audi Pet Project

## Содержание
1. [Обзор](#обзор)
2. [Начало работы](#начало-работы)
3. [Архитектура](#архитектура)
4. [Компоненты](#компоненты)
5. [Стилизация](#стилизация)
6. [Оптимизация](#оптимизация)
7. [Тестирование](#тестирование)
8. [Развертывание](#развертывание)

---

## Обзор

**Audi Pet Project** - современный учебный проект веб-сайта премиум-марки автомобилей Audi. Проект демонстрирует качественную верстку, восприимчивый дизайн и профессиональный подход к веб-разработке.

### Основные характеристики
- ✅ Семантическая HTML5 разметка
- ✅ Адаптивный CSS3 дизайн
- ✅ Оптимизированные изображения и видео
- ✅ Кроссбраузерная совместимость
- ✅ Фирменная типографика (AudiType)
- ✅ Доступность (WCAG AA)

### Стек технологий
```
Frontend:
  - HTML5
  - CSS3
  - SVG для логотипов
  - Растровая графика (PNG, JPG)
  - Видео (MP4)

Дизайн:
  - Шрифты: AudiType Extended
  - Расцветка: Минималистичная, темная
  - Макет: Flexbox, Grid (при необходимости)
```

---

## Начало работы

### Предварительные требования
- Git для версионирования
- Текстовый редактор (VS Code, Sublime, Atom)
- Браузер для тестирования
- Локальный HTTP сервер (опционально)

### Установка

```bash
# Клонирование
git clone https://github.com/neizer4ik46-jpg/audi-pet-project.git
cd audi-pet-project

# Запуск (выберите один вариант)
python -m http.server 8000          # Python
http-server                          # Node.js
php -S localhost:8000               # PHP
```

### Первые шаги
1. Откройте `http://localhost:8000`
2. Откройте DevTools (F12)
3. Работайте с HTML/CSS файлами
4. Проверяйте изменения в браузере

---

## Архитектура

### Общая структура

```
┌─────────────────────────────┐
│    index.html (разметка)    │
├─────────────────────────────┤
│  │
│  ├─ <head>
│  │   ├─ Meta tags
│  │   ├─ Title
│  │   ├─ Favicon link
│  │   └─ CSS links
│  │
│  └─ <body>
│      ├─ <header> - Шапка сайта
│      ├─ <nav> - Навигация
│      ├─ <main> - Основной контент
│      └─ <footer> - Подвал (если есть)
│
├─────────────────────────────┤
│  css/reset.css + style.css  │ ← Стили
├─────────────────────────────┤
│  fonts/ (AudiType)          │ ← Типографика
├─────────────────────────────┤
│  images/                    │ ← Визуальный контент
└─────────────────────────────┘
```

### Разделение ответственности

**HTML (index.html)**
- Структура контента
- Семантика
- Доступность (ARIA)
- SEO метаданные

**CSS (reset.css + style.css)**
- Визуальное представление
- Адаптивные макеты
- Анимации (если есть)
- Типографика

**Assets (fonts/, images/)**
- Шрифты для типографики
- Изображения (оптимизированные)
- Видео контент
- Иконки (favicon)

---

## Компоненты

### Header (Шапка)
```html
<header class="site-header">
    <div id="header-logo">
        <a href="index.html">
            <svg><!-- Логотип Audi --></svg>
        </a>
    </div>
    <nav>
        <ul class="header-menu">
            <!-- Пункты меню -->
        </ul>
    </nav>
</header>
```

**Стили:**
- `flex-center` - центрирование через Flexbox
- `.site-header` - основной класс шапки
- `.header-menu` - список меню
- `.header-submenu` - подменю

### Навигация (Navigation)
```html
<nav class="flex-center site-header">
    <ul class="header-menu">
        <li>
            <a class="arrow">Company</a>
            <ul class="header-submenu"></ul>
        </li>
    </ul>
</nav>
```

**Функциональность:**
- Основное меню с пунктами
- Подменю (dropdown) при наведении
- ARIA атрибуты для доступности
- Адаптивная мобильная версия

### Главный контент
Содержит:
- Блоки с описанием
- Изображения и видео
- Кнопки вызова действия (CTA)
- Информационные секции

---

## Стилизация

### CSS структура

#### reset.css
Нормализация стилей:
```css
/* Удаление стандартных отступов */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Нормализация элементов */
body, html {
    height: 100%;
}

img, video {
    max-width: 100%;
    height: auto;
}
```

#### style.css
Основные стили:
```css
/* Переменные CSS */
:root {
    --primary-color: #000;
    --secondary-color: #fff;
    --accent-color: #c5c5c5;
}

/* Основные классы */
.flex-center {
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Типографика */
body {
    font-family: 'AudiTypeNormal', sans-serif;
    color: var(--primary-color);
}

h1, h2 {
    font-family: 'AudiTypeBold', sans-serif;
}

/* Адаптивность */
@media (max-width: 768px) {
    /* Мобильные стили */
}
```

### Адаптивный дизайн

**Breakpoints:**
- **≥ 1920px** - Десктопная версия (HD)
- **≥ 1024px** - Планшет (Landscape)
- **≥ 768px** - Планшет (Portrait)
- **≥ 480px** - Мобильный (Large)
- **< 480px** - Мобильный (Small)

**Пример:**
```css
/* Desktop first */
.container {
    width: 1200px;
    margin: 0 auto;
}

@media (max-width: 1024px) {
    .container {
        width: 100%;
        padding: 0 20px;
    }
}

@media (max-width: 768px) {
    .container {
        width: 100%;
        padding: 0 15px;
    }
}
```

---

## Оптимизация

### Производительность

#### Изображения
- Оптимальные размеры:
  - Промо: 1920×1080px
  - Стандарт: 800×600px
  - Иконки: 32×32px до 256×256px

#### Видео
- Кодек: H.264
- Формат: MP4
- Битрейт: 2-5 Mbps
- Атрибуты: `preload="none"` `poster="image.jpg"`

#### Кэширование
```html
<!-- Версионирование статических файлов -->
<link rel="stylesheet" href="css/style.css?v=1.0.0">
<img src="images/photo.png?v=1.0.0" />
```

### SEO оптимизация

```html
<!-- Meta теги -->
<meta name="description" content="...">
<meta name="keywords" content="...">
<meta name="author" content="...">
<meta property="og:title" content="...">
<meta property="og:image" content="...">
```

### Доступность (A11y)

```html
<!-- ARIA атрибуты -->
<nav aria-label="Main navigation">
    <ul>
        <li><a href="#" aria-current="page">Home</a></li>
    </ul>
</nav>

<!-- Альтернативный текст -->
<img src="photo.png" alt="Describing text">

<!-- Семантические теги -->
<header>, <nav>, <main>, <article>, <section>, <footer>
```

---

## Тестирование

### Что тестировать

#### Браузеры
- Chrome (Windows, macOS, Linux)
- Firefox (Windows, macOS, Linux)
- Safari (macOS, iOS)
- Edge (Windows)

#### Устройства
- Десктопы (21-27" экраны)
- Планшеты (7", 10" экраны)
- Мобильные (3.5"-6.5" экраны)

#### Проверки
- ✓ Загрузка всех ресурсов
- ✓ Корректно отображение на всех размерах
- ✓ Нет консольных ошибок
- ✓ Функциональность кнопок и ссылок
- ✓ Скорость загрузки < 3 сек
- ✓ Доступность (Tab навигация)

### Инструменты тестирования

```bash
# Проверка производительности
# https://developers.google.com/speed/pagespeed/insights

# Проверка доступности
# https://www.deque.com/axe/devtools/

# Валидация кода
# https://validator.w3.org/
# https://jigsaw.w3.org/css-validator/
```

---

## Развертывание

### Хостинг опции

#### GitHub Pages (Бесплатно)
```bash
# Отправить на ветку gh-pages
git push origin master:gh-pages

# Доступно по адресу:
# https://neizer4ik46-jpg.github.io/audi-pet-project/
```

#### Vercel (Рекомендуется)
1. Регистрация на https://vercel.com
2. Импорт GitHub репозитория
3. Автоматическое развертывание при push

#### Netlify
1. Регистрация на https://netlify.com
2. Подключение GitHub
3. Выбор ветки для публикации

#### Традиционный хостинг
```bash
# Загрузить FTP или SFTP
# - index.html
# - css/
# - fonts/
# - images/

# Убедитесь, что пути к ресурсам корректны
```

### Оптимизация для production

```html
<!-- Минифицированные ссылки -->
<link rel="stylesheet" href="css/style.min.css">

<!-- Версионирование -->
<script src="js/main.js?v=1.0.0"></script>

<!-- Кэширование -->
<meta http-equiv="Cache-Control" content="max-age=31536000">
```

---

## Troubleshooting

### Частые проблемы

| Проблема | Решение |
|----------|----------|
| Шрифты не загружаются | Проверьте пути в @font-face |
| Изображения не видны | Убедитесь в корректных путях |
| Стили не применяются | Очистите кеш (Ctrl+F5) |
| Рендеринг медленный | Оптимизируйте изображения |
| CORS ошибки | Используйте локальный сервер |

---

## Ресурсы

### Документация
- [MDN Web Docs](https://developer.mozilla.org/)
- [W3C HTML Specification](https://www.w3.org/TR/html5/)
- [CSS-Tricks](https://css-tricks.com/)

### Интструменты
- [VS Code](https://code.visualstudio.com/)
- [Chrome DevTools](https://developer.chrome.com/docs/devtools/)
- [Can I Use](https://caniuse.com/)

### Оптимизация
- [TinyPNG](https://tinypng.com/) - Сжатие изображений
- [ImageOptim](https://imageoptim.com/) - Оптимизация
- [Google PageSpeed](https://developers.google.com/speed/pagespeed/insights)

---

**Версия документации:** 1.0.0  
**Дата обновления:** 25 марта 2026  
**Разработчик:** Nazar Neruk

