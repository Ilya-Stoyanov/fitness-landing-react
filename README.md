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

### Подключение Tailwind и шрифтов
- Шрифты подключены через @import, используются @theme переменные.

```bash
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,100..1000;1,100..1000&family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

@import "tailwindcss";

@theme {
    --font-*: initial;
    --font-dmsans: "DM Sans", "sans-serif";
    --font-montserrat: "Montserrat", "serif";
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

### Больше уроков 

[YouTube](https://www.youtube.com/channel/UCStPiUDdMG-aJPziQyqVZVg/)