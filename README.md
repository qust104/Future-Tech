<div align="center">

# 🚀 Future Tech
### AI & Technology News Portal

Современный многостраничный новостной портал о технологиях и ИИ.  
Полностью адаптивный сайт с кастомными интерактивными компонентами на **Vanilla JavaScript** и **БЭМ**-методологии.

<p>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Sass-CC6699?style=flat&logo=sass&logoColor=white" alt="Sass">
</p>

[🔗 **Live Demo**](https://qust104.github.io/Future-Tech/index.html) · [🛠 Технологии](#-технологии) · [✨ Возможности](#-ключевые-возможности)

</div>

---

## 🛠 Технологии

| Категория | Стек                                   |
|---|----------------------------------------|
| **Frontend** | HTML5, CSS3, SCSS, JavaScript (ES6+)   |
| **Библиотеки** | IMask.js (маски ввода тел. номера)     |
| **Методологии** | БЭМ, ООП, Component-based Architecture |
| **Build** | Sass, npm                              |

---

## ✨ Ключевые возможности

- 📱 **6 полностью адаптивных страниц** — главная, новости, подкасты, ресурсы, блог, контакты
- 🎨 **46+ переиспользуемых БЭМ-компонентов** — модульная архитектура
- ⚙️ **Vanilla JavaScript без фреймворков** — чистая архитектура с ООП
- 🎯 **Реактивное управление состоянием** — через Proxy API (как в Vue/React)
- 📑 **Табы с keyboard navigation** — Arrow keys, Home, End, полная ARIA-поддержка
- 🔍 **Кастомный Select** — адаптивный dropdown, нативный на mobile
- 🎬 **Кастомный видеоплеер** — управление воспроизведением
- 🍔 **Мобильное меню** — overlay с блокировкой скролла

---

## 💻 JavaScript Архитектура

### BaseComponent — реактивность через Proxy API

```javascript
class BaseComponent {
    getProxyState(initialState = {}) {
        return new Proxy(initialState, {
            set: (target, prop, newValue) => {
                const oldValue = target[prop]
                target[prop] = newValue
                if (newValue !== oldValue) {
                    this.updateUI()  // Автоматическое обновление UI
                }
                return true
            }
        })
    }
}
```

**Преимущества:**
- ✅ Реактивность без фреймворков
- ✅ Автоматическое обновление DOM
- ✅ Централизованное управление состоянием

### Collection Pattern

```javascript
class TabsCollection {
    constructor() {
        document.querySelectorAll('[data-js-tabs]')
            .forEach(element => new Tabs(element))
    }
}
```

**Преимущества:**
- ✅ Автоматическая инициализация всех экземпляров
- ✅ DRY principle
- ✅ Легкая масштабируемость

### Реализованные модули

| Модуль | Описание |
|---|---|
| **Tabs** | Полная клавиатурная навигация, ARIA compliant |
| **Select** | Адаптивный positioning, progressive enhancement для mobile |
| **VideoPlayer** | Управление нативным видео |
| **ExpandableContent** | Web Animations API для плавной анимации |
| **Header** | Мобильное меню с управлением скроллом |
| **InputMask** | Интеграция IMask.js |

---

## 🎨 CSS/SCSS

### БЭМ + современный SCSS

```scss
// Adaptive Typography через clamp()
@function fluid($max: 100, $min: 10) {
    @return clamp(#{$min}rem, calc(...), #{$max}rem);
}

h1 { font-size: fluid(70, 30); }  // 70px → 30px адаптивно

// Миксины
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

@mixin hover {
    @media (hover: hover) { &:hover { @content; } }
}
```

**Особенности:**
- ✅ Строгая БЭМ методология
- ✅ CSS Custom Properties для theming
- ✅ Fluid Typography через `clamp()`
- ✅ 5 breakpoints (Desktop → Mobile-S)
- ✅ Touch-friendly (минимум 44px для кнопок)

---

## 🚀 Установка

```bash
# Клонировать репозиторий
git clone https://github.com/qust104/Future_Tech.git
cd Future_Tech/future-tech

# Установить зависимости
npm install

# Запустить SASS в watch режиме
npm run sass-watch
```

> Откройте проект через локальный сервер (Live Server, http-server) или встроенный сервер вашей IDE.

---

## 🏗 Структура проекта

```
src/
├── scripts/
│   ├── BaseComponent.js      # Абстрактный класс с Proxy
│   ├── Tabs.js               # Табы с keyboard nav
│   ├── Select.js             # Кастомный select
│   ├── VideoPlayer.js        # Видеоплеер
│   └── main.js               # Entry point
├── styles/
│   ├── blocks/                # 46 БЭМ компонентов
│   ├── helpers/                # Functions, mixins, media
│   └── main.scss
├── index.html                  # Главная
├── news.html                   # Новости
├── podcasts.html                # Подкасты
├── resources.html                # Ресурсы
├── blog.html                      # Блог
└── contacts.html                   # Контакты
```

---

## 💎 Качество кода

- ✅ Чистая архитектура на Vanilla JavaScript
- ✅ Реактивное управление состоянием (Proxy API)
- ✅ Component-based подход с наследованием
- ✅ Строгая БЭМ методология
- ✅ ARIA compliant + keyboard navigation
- ✅ Adaptive design (5 breakpoints)
- ✅ ES6+ (Classes, Modules, Arrow Functions)
- ✅ Web APIs (Proxy, Web Animations, matchMedia)

---

## 🌐 Browser Support

**Desktop:** Chrome, Firefox, Safari, Edge (последние 2 версии)
**Mobile:** iOS Safari, Chrome Mobile

**Используемые возможности:** CSS Grid, Flexbox, CSS Variables, `clamp()`, ES6+, Proxy API, Web Animations API

---

## 👤 Автор

<div align="center">

🐙 GitHub: [@qust104](https://github.com/qust104)  
📧 Email: az1023415@gmail.com  
💬 Telegram: [@Ninekidoru](https://t.me/Ninekidoru)

</div>

