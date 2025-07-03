# Fitness Landing Page (React + TypeScript + Vite + Tailwind CSS)

## Installation

### Установка Node.js  
Скачай и установи **Node.js** с [официального сайта](https://nodejs.org/en/download).

### Установка npm (если нужно обновить)

```bash
npm install -g npm
```

## Как развернуть проект
- Открываешь GitHub Desktop
- Нажимаешь File → Clone Repository...
- Вставляешь ссылку на репозиторий:

```bash
https://github.com/Ilya-Stoyanov/fitness-landing-react
```

- Выбираешь папку для проекта и нажимаешь Clone
- Открываешь терминал в папке проекта и выполняешь:

```bash
npm install
```

### Запуск проекта

```bash
npm run dev
```
### Используемые технологии
- React 19 (react, react-dom)
- Vite (vite, @vitejs/plugin-react)
- TypeScript
- Tailwind CSS 4 (tailwindcss, postcss)
- Framer Motion (анимации)
- React Scroll (плавный скроллинг)

### Подключение Tailwind и шрифтов index.css
- Шрифты подключены через @import, используются @theme переменные.

```bash
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,100..1000;1,100..1000&family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

@import "tailwindcss";

@theme {
    --font-*: initial;
    --font-dmsans: "DM Sans", "sans-serif";
    --font-montserrat: "Montserrat", "serif";

    --color-gray-20: #F8F4EB;
    --color-gray-50: #EFE6E6;
    --color-gray-100: #DFCCCC;
    --color-gray-500: #5E0000;

    --color-primary-100: #FFE1E0;
    --color-primary-300: #FFA6A3;
    --color-primary-500: #FF6B66;

    --color-secondary-400: #FFCD5B;
    --color-secondary-500: #FFC132;

    --background-gradient-yellowred: linear-gradient(90deg, #FF616A 0%, #FFC837 100%);
    --background-mobile-home: url('./assets/HomePageGraphic.png');

    --content-evolvetext: url('./assets/EvolveText.png'); 
    --content-evolvetextconact: url('./assets/EvolveTextContact.png'); 
    --content-abstractwaves: url('./assets/AbstractWaves.png');
    --content-sparkles: url('./assets/Sparkles.png');
    --content-circles: url('./assets/Circles.png');

    --breakpoint-*: initial; /* Сброс стандартных брейкпоинтов */
    --breakpoint-xs: 30rem;   /* 480px */
    --breakpoint-sm: 48rem;   /* 768px */
    --breakpoint-md: 66.25rem; /* 1060px */
}

html,
body,
#root,
.app {
    min-height: 100vh;
    width: 100%;
    overflow-x: hidden;
    font-family: var(--font-dmsans);
    scroll-behavior: smooth;
}

.swiper-button-next:after,
.swiper-button-prev:after {
    content: 'next';
    color: #ffc132;
    border-radius: 50px;
    font-weight: 900;
}

#ourclasses .swiper{
    padding-bottom: 50px;
}

#ourclasses .swiper-pagination-bullet-active{
    background: #FF616A;
}

#ourclasses .swiper-pagination-bullet{
    width: 12px;
    height: 12px;
}

@media(max-width:1124px) {

    .swiper-button-next:after,
    .swiper-button-prev:after {
        display: none;
    }
}

```
### Главный компонент App.tsx

- Применяются font-montserrat и font-dmsans.

```bash
function App() {
  return (
    <div className="flex-col justify-center gap-2.5">
      <h1 className="text-2xl">My fitness project</h1>
      <p className="font-montserrat">Текст с Montserrat</p>
      <p className="font-dmsans">Текст с DM Sans</p>
    </div>
  )
}

export default App
```

### Точка входа main.tsx

```bash
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.tsx'

createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <App />
  </StrictMode>,
)
```

### Проверь settings.json в VS Code
- Открой настройки (Ctrl + Shift + P → Open Settings (JSON)) и добавь эти параметры:

```sh
{
  "editor.quickSuggestions": {
    "strings": true
  },
  "tailwindCSS.includeLanguages": {
    "javascript": "javascript",
    "typescript": "typescript",
    "javascriptreact": "javascript",
    "typescriptreact": "typescript"
  },
  "tailwindCSS.experimental.classRegex": [
    "clsx\\(([^)]*)\\)",
    "cn\\(([^)]*)\\)"
  ]
}

```

### Section Home

#### Text 
- Unrivaled Gym. Unparalleled Training Fitness Classes. World Class Studios to get the Body Shapes That you Dream of.. Get Your Dream Body Now.

- Join Now

- Learn More

```sh
export const sponsorImages = [
    { src: SponsorRedBull, alt: "Sponsor-RedBull" },
    { src: SponsorForbes, alt: "Sponsor-Forbes" },
    { src: SponsorRedBull, alt: "Sponsor-RedBull" },
    { src: SponsorForbes, alt: "Sponsor-Forbes" },
    { src: SponsorFortune, alt: "Sponsor-Fortune" },
];

```

### Больше уроков 

[YouTube](https://www.youtube.com/channel/UCStPiUDdMG-aJPziQyqVZVg/)