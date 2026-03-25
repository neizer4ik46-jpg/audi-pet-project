# Руководство по настройке и запуску проекта

## Быстрый старт (Quick Start)

### 1. Клонирование проекта
```bash
git clone https://github.com/neizer4ik46-jpg/audi-pet-project.git
cd audi-pet-project
```

### 2. Запуск проекта

#### Вариант A: Прямой запуск в браузере
```bash
# Просто откройте файл в браузере
index.html  # Двойной клик или drag-and-drop
```

#### Вариант B: Локальный HTTP сервер (Рекомендуется)

**Python 3:**
```bash
python -m http.server 8000
# Затем откройте http://localhost:8000
```

**Python 2:**
```bash
python -m SimpleHTTPServer 8000
# Затем откройте http://localhost:8000
```

**Node.js (http-server):**
```bash
npm install -g http-server
http-server
# Откройте http://localhost:8080
```

**PHP:**
```bash
php -S localhost:8000
# Затем откройте http://localhost:8000
```

#### Вариант C: VS Code Live Server
1. Установите расширение "Live Server" (автор: Ritwick Dey)
2. Нажмите правой кнопкой на `index.html`
3. Выберите "Open with Live Server"
4. Браузер откроется автоматически с обновлением при изменениях

## Требования

### Минимальные требования
- Браузер с поддержкой HTML5 и CSS3
- Экран с разрешением 320px и выше (мобильная разметка)

### Рекомендуемые требования
- **ОС:** Windows, macOS, Linux
- **Браузер:** Chrome/Edge (последняя версия)
- **Уровень:**  базовые знания HTML/CSS
- **Редактор:** VS Code, Sublime Text, Atom

### Поддерживаемые браузеры

| Браузер | Версия | Поддержка |
|---------|--------|-----------|
| Chrome | 90+ | Полная ✅ |
| Firefox | 88+ | Полная ✅ |
| Safari | 14+ | Полная ✅ |
| Edge | 90+ | Полная ✅ |
| Opera | 76+ | Полная ✅ |
| IE 11 | - | Базовая ⚠️ |

## Установка на разные ОС

### Windows

#### Python 3 (рекомендуется)
1. Установите [Python 3](https://www.python.org/)
2. Откройте Command Prompt в папке проекта
3. Выполните: `python -m http.server 8000`
4. Откройте: `http://localhost:8000`

#### Node.js
```bash
npm install -g http-server
http-server
```

### macOS

#### Python (встроен по умолчанию)
```bash
python3 -m http.server 8000
# или
python -m http.server 8000
```

#### Homebrew + Node.js
```bash
brew install node
npm install -g http-server
http-server
```

### Linux

#### Python
```bash
python3 -m http.server 8000
```

#### Apache
```bash
sudo apt install apache2
# Скопируйте файлы в /var/www/html/
# Откройте http://localhost
```

## Структура папок при запуске

```
audi-pet-project/
├── index.html
├── css/
│   ├── reset.css
│   └── style.css
├── fonts/
│   ├── auditype_extendedbold.ttf
│   └── auditype_extendednormal.ttf
├── images/
│   ├── copy/
│   ├── favicon/
│   └── original/
└── README.md
```

## Основные URL при локальной разработке

- `http://localhost:8000/` - Главная страница
- `http://localhost:8000/css/style.css` - Основные CSS
- `http://localhost:8000/images/` - Папка с изображениями

## Разработка и отладка

### Использование браузерных инструментов

1. **F12 или Right-click → Inspect** - Открыть DevTools
2. **Elements/Inspector** - Просмотр HTML структуры
3. **Styles** - Просмотр и редактирование CSS
4. **Console** - Проверка ошибок JavaScript
5. **Network** - Проверка загрузки ресурсов
6. **Performance** - Анализ производительности

### Проверка мобильной версии

В DevTools:
1. Нажмите **Ctrl+Shift+M** (Windows/Linux) или **Cmd+Shift+M** (Mac)
2. Выберите нужное устройство из списка
3. Тестируйте адаптивность

### Валидация кода

**HTML валидация:**
- Используйте [W3C HTML Validator](https://validator.w3.org/)
- Скопируйте исходный код и вставьте для проверки

**CSS валидация:**
- Используйте [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- Проверьте совместимость с браузерами

## Общие проблемы и решения

### Проблема: Изображения не загружаются
**Решение:** Проверьте пути в HTML файле
```html
<!-- Неправильно -->
<img src="images/photo.png" />

<!-- Правильно -->
<img src="./images/copy/photo.png" />
```

### Проблема: Шрифты не подгружаются
**Решение:** Проверьте пути в CSS файле и формат @font-face
```css
@font-face {
    font-family: 'AudiType';
    src: url('../fonts/auditype_extendednormal.ttf') format('truetype');
}
```

### Проблема: CSS не применяется
**Решение:**
1. Очистите кеш браузера (Ctrl+Shift+Delete)
2. Проверьте путь в теге `<link>`
3. Убедитесь, что файл style.css существует

### Проблема: "Ошибка CORS" при локальном запуске
**Решение:** Используйте локальный сервер (не открывайте file://)

## Оптимизация производительности

### Изображения
- Сжимайте изображения перед загрузкой
- Используйте WebP для современных браузеров
- Устанавливайте атрибуты `width` и `height`

### CSS
- Минифицируйте production версию
- Удаловайте неиспользуемые стили
- Используйте CSS переменные для повтора

### Видео
- Сжимайте видео перед загрузкой
- Используйте правильный кодек (h.264)
- Добавьте атрибут `preload="none"`

## Версионирование

Текущая версия: **1.0.0**

Для отслеживания версий используйте Git tags:
```bash
git tag v1.0.0
git push origin v1.0.0
```

## Получение помощи

### Ресурсы
- [MDN Web Docs](https://developer.mozilla.org/)
- [W3C](https://www.w3.org/)
- [Can I Use](https://caniuse.com/)

### Контакты
- **GitHub Issues:** https://github.com/neizer4ik46-jpg/audi-pet-project/issues
- **Email:** [указать email разработчика]

## Следующие шаги

После успешного запуска:
1. Изучите структуру HTML файла
2. Экспериментируйте с CSS стилями
3. Проверьте адаптивность на разных устройствах
4. Модифицируйте контент под свои нужды

---

**Успешной разработки! Happy Coding! 🚀**

Дата: 25 марта 2026
