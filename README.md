[![Liga A](./public/icons/logo.svg)](https://ligaa.agency/)

![Tech stack](https://skillicons.dev/icons?i=react,next,ts,sass)

# Гайд по работе

Для начала работы необходимы:
- [Node.js](https://nodejs.org/en/download/prebuilt-installer) 20 версии
- Пакетный менеджер [yarn](https://classic.yarnpkg.com/lang/en/docs/install/) `npm install --global yarn`

## 🐱‍💻 Команды

| Command                  | Action                                          |
|:-------------------------|:------------------------------------------------|
| `yarn install`           | Установить зависимости                          |
| `yarn run dev`           | Запустить локальный дев сервер `localhost:3000` |
| `yarn run build`         | Создать оптимизированный production build       |
| `yarn run start`         | Запустить production build                      |
| `yarn run lint`          | Запустить линтер                                |
| `yarn run stylelint`     | Запустить линтер стилей                         |
| `yarn run prettier`      | Фрорматировать код с настройками prettier       |
| `yarn run check`         | Запустить проверку линтерами и форматирование   |
| `yarn run gen:component` | Утилита для создания шаблонного компонента      |

## 🚀 Структура
Используется модульная архитектура

Нижележащий слой может испльзоваться только в слоях стоящих выше по иерархии

### `shared 🡒 ui 🡒 service 🡒 components 🡒 modules 🡒 views 🡒 app`

**Для генерации компонентов используйте утилиту `yarn run gen:component`**

```text
├── public/                 # статические файлы (иконки, картинки и тп.)
│   ├── icons/
│   ├── images/
│   ├── ...
│   ├── favicon.ico
│   └── robots.txt
├── src/
│   ├── app/                # next app router
│   │   ├── fonts/          # шрифты для локального подключения next/font
│   │   ├── ...
│   │   ├── layout.tsx
│   │   └── page.tsx
│   ├── components/         # компоненты ( могут обладать бизнес-логикой )
│   │   ├── dialog/
│   │   ├── ...
│   │   └── index.ts
│   ├── modules/            # модули ( могут иметь вложенные компоненты, своё состояние и изолированную логику )
│   │   ├── footer/
│   │   ├── header/
│   │   └── ...
│   ├── service/            # сервисы ( провайдеры, порталы и подобные им сущности )
│   │   ├── portal/
│   │   ├── provider/
│   │   └── ...
│   ├── shared/             # общее ( переиспользуемые глобальные сущности не имеющие конкретной привязки )
│   │   ├── api/
│   │   ├── assets/
│   │   ├── atoms/
│   │   ├── const/
│   │   ├── hooks/
│   │   ├── styles/
│   │   └── types/
│   ├── ui/                 # элементы интерфейса ( базовые переиспользуемые ui компоненты )
│   │   ├── button/
│   │   ├── ...
│   │   └── index.ts
│   └── views/              # страницы ( лэйауты страниц )
│       ├── home/
│       └── ...
├── util/                   # утилиты ( автоматизация процессов и тп. )
│   ├── component/
│   └── ...
├── package.json
└── ...
```

## 🎴 Картинки

Для оптимизации изображений используйте компонент [next/image](https://nextjs.org/docs/app/building-your-application/optimizing/images)

## ♠️ Иконки

SVG графика для импорта в качестве компонента хранится в директории `src/shared/assets/icons`

Импортируется как компонент:

```typescript jsx
import Icon from '@icons/icon.svg'

const IconExample = () => (
  <div>
    <Icon />
  </div>
)
```
