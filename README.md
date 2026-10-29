# PROJECT Z — сайт сервера (CS:S v34)

Статический сайт-портал для серверов **PROJECT Z** (Zombie Mod / Zombie Escape).
Чистый HTML/CSS/JS — работает где угодно, в т.ч. на **GitHub Pages** бесплатно.

## Структура
```
projectz-website/
├─ index.html        ← главная страница
├─ css/style.css     ← стили (тёмная тема)
├─ js/main.js        ← копирование IP, пароль, меню
└─ README.md         ← этот файл
```

## Как открыть локально
Просто дважды кликни по **index.html** — откроется в браузере.

## Как выложить на GitHub Pages (бесплатный хостинг)

### Вариант А — через сайт github.com (проще)
1. Зайди на https://github.com → **New repository**.
2. Имя: например `projectz-site` → **Public** → **Create repository**.
3. На странице репозитория: **Add file → Upload files**.
4. Перетащи **содержимое** папки `projectz-website` (файл `index.html`, папки `css` и `js`) → **Commit changes**.
5. **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main** / `/root` → **Save**.
6. Через ~1 минуту сайт будет по адресу:
   `https://ТВОЙ_ЛОГИН.github.io/projectz-site/`

### Вариант Б — через Git (если установлен)
```bash
cd projectz-website
git init
git add .
git commit -m "PROJECT Z site"
git branch -M main
git remote add origin https://github.com/ТВОЙ_ЛОГИН/projectz-site.git
git push -u origin main
```
Потом включи Pages в **Settings → Pages** (как в шаге 5 выше).

## Что уже работает
- 🎮 Кнопка **«Подключиться»** → запускает `steam://connect/46.174.54.162:27015`
- 📋 Кнопка **«Скопировать IP»** и клик по самому IP → копирует адрес в буфер
- 👁️ Показ/скрытие пароля, мобильное меню, активная вкладка при прокрутке

## Что нужно поправить под себя
Открой `index.html` и замени:
- **IP и порт** второго сервера (сейчас у обоих `46.174.54.162:27015`)
- **Ссылку на Discord** — найди `class="card discord"` и `btn-discord`, вставь свой инвайт в `href`
- **Счётчики игроков / статистику** — это статичные цифры (на GitHub Pages нельзя опрашивать игровой сервер из браузера). Для «живого» онлайна нужен внешний сервис (напр. game-monitor / виджет) или свой бэкенд.

## Важно про «живой онлайн»
GitHub Pages — это статика (без сервера), поэтому реальное число игроков браузер напрямую с CS-сервера получить не может. Варианты позже:
- вставить готовый виджет мониторинга (gametracker/game-monitor),
- или поднять небольшой бэкенд, который опрашивает сервер и отдаёт JSON.

Сейчас цифры заданы вручную в `index.html` — меняй их там.
