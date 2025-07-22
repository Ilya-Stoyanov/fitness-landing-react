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

### Section Benefits

#### Text

- MORE THAN JUST GYM
- We provide world class fitness equipment, trainers and classes to
  get you to your ultimate fitness goals with ease. We provide true
  care into each and every member.
- MILLIONS OF HAPPY MEMBERS GETTING
- FIT

- Nascetur aenean massa auctor tincidunt. Iaculis potenti amet
  egestas ultrices consectetur adipiscing ultricies enim. Pulvinar
  fames vitae vitae quis. Quis amet vulputate tincidunt at in
  nulla nec. Consequat sed facilisis dui sit egestas ultrices
  tellus. Ullamcorper arcu id pretium sapien proin integer nisl.
  Felis orci diam odio.
- Fringilla a sed at suspendisse ut enim volutpat. Rhoncus vel est
  tellus quam porttitor. Mauris velit euismod elementum arcu neque
  facilisi. Amet semper tortor facilisis metus nibh. Rhoncus sit
  enim mattis odio in risus nunc.

```sh

export type BenefitType = {
  icon?: JSX.Element;
  title: string;
  description: string;
};

# DataBenefits

import {BenefitType} from "@/types/type";
import { HiHomeModern, HiMiniUserGroup, HiAcademicCap } from "react-icons/hi2";


export const benefits: Array<BenefitType> = [
    {
      icon: <HiHomeModern className="h-6 w-6" />,
      title: "State of the Art Facilities",
      description:
        "Neque adipiscing amet amet enim. Feugiat dolor enim fermentum in a in lectus pellentesque. Ullamcorper et.",
    },
    {
      icon: <HiMiniUserGroup className="h-6 w-6" />,
      title: "100's of Diverse Classes",
      description:
        "Eu ipsum id egestas risus tempus enim semper felis quis. Nec consectetur ac venenatis facilisi est. Eget ac turpis id.",
    },
    {
      icon: <HiAcademicCap className="h-6 w-6" />,
      title: "Expert and Pro Trainers",
      description:
        "Fusce vestibulum aliquam ut cras. Nisl lectus egestas sapien nisl. Lacus at mi sit pellentesque. Congue parturient.",
    },
];

```

### Section our Classes

#### Text

- OUR CLASSES
- Fringilla a sed at suspendisse ut enim volutpat. Rhoncus vel est tellus quam porttitor. Mauris velit euismod elementum arcu neque facilisi. Amet semper tortor facilisis metus nibh. Rhoncus sit enim mattis odio in risus nunc.

```sh
export type ClassType = {
  title: string;
  description?: string;
  image: string;
};

# classesData

import image1 from "@/assets/image1.png";
import image2 from "@/assets/image2.png";
import image3 from "@/assets/image3.png";
import image4 from "@/assets/image4.png";
import image5 from "@/assets/image5.png";
import image6 from "@/assets/image6.png";

export const classesData: Array<ClassType> = [
  {
    title: "Weight Training Classes",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: image1,
  },
  {
    title: "Yoga Classes",
    image: image2,
  },
  {
    title: "Ab Core Classes",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: image3,
  },
  {
    title: "Adventure Classes",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: image4,
  },
  {
    title: "Fitness Classes",
    image: image5,
  },
  {
    title: "Training Classes",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
    image: image6,
  },
];

```

### Больше уроков

[YouTube](https://www.youtube.com/channel/UCStPiUDdMG-aJPziQyqVZVg/)
