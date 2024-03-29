<p align="center">
    <img
      src="https://www.gatsbyjs.com/Gatsby-Logo.svg"
      width="400"
      alt="Gatsby.js Logo"
    />
</p>


# Gatsby.js: Руководство разработчика

### Содержание

1. [Что такое Gatsby.js](#что-такое-gatsbyjs)
   1. [Что такое SSG](#что-такое-ssg)
   2. [Какую проблему решает Gatsby](#какую-проблему-решает-gatsby)
2. [Настройка окружения](#настройка-окружения)
   1. [Gatsby CLI](#gatsby-cli)
      1. [Базовые команды](#базовые-команды)
      2. [Создание сайта и Gatsby Starters](#создание-сайта-и-gatsby-starters)
   2. [Шпаргалка по основным командам Gatsby](#шпаргалка-по-основным-командам-gatsby)
   3. [Настройка GitHub репозитория для Gatsby сайта](#настройка-gitHub-репозитория-для-gatsby-сайта)
3. [Структура Gatsby сайта](#структура-gatsby-сайта)
   1. [Папки](#папки)
   2. [Файлы](#файлы)
4. [Создание страниц в Gatsby](#создание-страниц-в-gatsby)
5. [Добавление метаданных](#добавление-метаданных)
6. [Ссылки на страницы. Компонент &lt;Link&gt;](#ссылки-на-страницы-компонент-link)
7. [Общие компоненты страницы](#общие-компоненты-страницы)
8. [Создание макета страниц. Шаблон &lt;Layout&gt;](#создание-макета-страниц-шаблон-layout)
9. [Стилизация компонентов](#стилизация-компонентов)
   1. [Стилизация с помощью CSS модулей](#стилизация-с-помощью-css-модулей)
   2. [Добавление поддержки Sass/SCSS](#добавление-поддержки-sassscss)
10. [Работа с GraphQL](#работа-с-graphql)
    1. [Использование инструмента GraphiQL](#использование-инструмента-graphiql)
    2. [Подключение GraphQL Playground](#подключение-graphql-playground)
    3. [Запросы в базовый компонент-конструктор. Использование useStaticQuery](#запросы-в-базовый-компонент-конструктор-использование-usestaticquery)
    4. [Запросы в компонентах страницы. Работа с файловой системой](#запросы-в-компонентах-страницы-работа-с-файловой-системой)
    5. [Составление запроса и выборка данных. Плагин gatsby-source-filesystem](#составление-запроса-и-выборка-данных-плагин-gatsby-source-filesystem)
11. [Создание страниц сайта](#создание-страниц-сайта)
    1. [Генерация ссылок на публикации. API onCreateNode](#генерация-ссылок-на-публикации-api-oncreatenode)
    2. [Генерация новой страницы для каждой публикации. API createPages](#генерация-новой-страницы-для-каждой-публикации-api-createpages)
    3. [Трансформация данных. Плагин gatsby-transformer-remark](#трансформация-данных-плагин-gatsby-transformer-remark)
    4. [Создание шаблона страницы публикации](#создание-шаблона-страницы-публикации)
    5. [Добавление изображений к постам](#добавление-изображений-к-постам)
    6. [Страница 404](#страница-404)
12. [Gatsby + Contentful](#gatsby--contentful)
    1. [Установка и настройка окружения. Плагин gatsby-source-contentful](#установка-и-настройка-окружения-плагин-gatsby-source-contentful)
    2. [Запрос данных из источника Contentful](#запрос-данных-из-источника-contentful)
    3. [Вывод списка постов. Запрос allContentfulBlogPost](#вывод-списка-постов-запрос-allcontentfulblogpost)
    4. [Рендеринг публикации на странице. Запрос contentfulBlogPost](#рендеринг-публикации-на-странице-запрос-contentfulblogpost)
    5. [Настройка метаданных сайта. React Helmet](#настройка-метаданных-сайта-react-helmet)
    6. [Деплой сайта Gatsby](#деплой-сайта-gatsby)
    7. [Обновление данных сайта](#обновление-данных-сайта)


## Что такое Gatsby.js

Gatsby [появился](https://www.gatsbyjs.com/blog/gatsby-v1/) в 2017 году изначально как невероятно быстрый генератор статических сайтов на React.

_Gatsby_ – генератор статических сайтов с открытым исходным кодом, созданный поверх Node.js в основе которого лежит библиотека React в сочетании с GraphQL, Webpack и другими инструментами. В качестве источника данных может использовать Markdown-документы, MDX (Markdown с JSX), картинки и разные CMS, такие, как WordPress, Drupal, Sanity, Strapi, Shopify и др.

Gatsby также позволяет комбинировать данные из разных источников и отображать их вместе друг с другом, например на одной странице данные блога могут подтягиваться из CMS WordPress, а eCommerce составляющая из Shopify и Stripe.

Gatsby позволяет достаточно быстро генерировать страницы сайта, который в свою очередь представляется безопасным перед базовыми уязвимостями, масштабируемым перед резким возрастанием трафика и SEO-оптимизированным.

![The modern website landscape](https://www.gatsbyjs.com/_gatsby/image/d49511ec78e1558d287d9369f7e461d2/bf75211527615cb5847a1d5aa03a6f66/content-mesh-1.avif?eu=d22ac827db1a1edd7385f5f44649c8d2cef9ddacb17858ff1608df3d3c2522cb44edd51f16291701912ba464dbb9a0db5ceff4897ead7904fb8a8773ce6bdcd481dd0a265246c1838d8f3e852a8ce2588320e2e16af5707c1a82cd58906c666c47614b2fa481eea978687beab7f4d3ab8daa777a5d777c25c733449ad05d979867e50129907d5b2615fb2f3da260db78669ec6318a68323741d33993c3bfdbe8df4a01ef91c18860c9f2b23b6750b436ba&a=w%3D600%26h%3D367%26fm%3Davif%26q%3D75&cd=94a25c4bfa99c261ce604dbca49d3aaf)

На сегодня Gatsby это полноценный _open source_ фреймворк, поставляющий «из коробки» большое количество возможностей. Помимо этого Gatsby предоставляет более 3 000 плагинов расширяющие его функциональность.

### Что такое SSG

_SSG (Static Site Generator)_ – программный инструмент позволяющий создавать статичные HTML-документы из записей различных источников, будь то текстовые записи или из данных различных CMS. В отличие от традиционных платформ динамических веб-сайтов предоставляет множество преимуществ:

* лучшая производительность;
* более высокий уровень безопасности;
* сравнительно низкая стоимость масштабирования;
* удобство обслуживания.

### Какую проблему решает Gatsby

При разработке сайта среди прочих факторов учитывается 3 важных аспекта, которые должны быть соблюдены:

- Поисковая оптимизация (SEO);
- Скорость загрузки сайта;
- Простота обновления элементов интерфейса сайта.

При _обычном статическом сайте_ с множеством страниц решается проблема только с поисковой оптимизацией (SEO) сайта, но никак с его скоростью и возможностью быстро обновить дизайн интерфейса, это придётся сделать многократно на множестве однотипных страниц.

_Одностраничные приложения_ быстро загружаются и легко изменяют вид интерфейса, но закономерно проигрывают в плане SEO-оптимизации, т.к. все изменения происходят на одной странице.

_Server Side Rendering (SSR)_ сайты производят рендер страниц на сервере после каждого запроса по заранее заданному шаблону. Подход решает проблему SEO и в такой сайт легко вносить изменения, но теряется время на обработку каждого запроса на сервере.

_Static Site Generator (SSG)_ сайты на Gatsby закрывают все 3 аспекта, т.к. пользователю отдаются полностью отрендеренные страницы со всеми данными, которые были сформированы на моменте сборки сайта. Это быстро и легко обновляемо, т.к. статически сгенерированные сайты могут работать как одностраничные SPA-приложения. Однажды загруженные компоненты и ссылки страницы сохраняются в кэш, повторный доступ к которым осуществляется мгновенно.

Gatsby сочетает в себе генерацию статического сайта, отложенную генерацию статики и интеллектуальный рендеринг страниц с выборочной предварительной загрузки важного контента, даёт ощущение быстрого и высокопроизводительного сайта, что оказывает положительное влияние на показатели SEO и конверсии.

## Настройка окружения

### Gatsby CLI

_Gatsby CLI_ – утилита командной строки, устанавливается глобально и служит для запуска команд для разработки сайтов на Gatsby. Подробная [документация по Gatsby CLI](https://www.gatsbyjs.com/docs/reference/gatsby-cli) дана на официальной странице.

```console
npm install gatsby-cli -g
```

_Список доступных команд_

```console
gatsby --help
```

_Проверка текущей версии_

```console
gatsby --version
```

#### Базовые команды

* `gatsby develop` – запускает девелопмент-сборку сайта и сервер разработки для отслеживания вносимых изменений в режиме реального времени. Альтернативная команда `npm run develop`, если Gatsby CLI не был установлен глобально;
* `gatsby build` – запускает продакшн-сборку проекта и подготавливает сайт для развёртывания (deployment) в Сети;
* `gatsby serve` – предоставляет продакшн-сборку для тестирования сайта перед деплоем;
* `info` – информация о среде разработки и доступных обновлениях, используется в отчётах об ошибках;
* `clean` – очищает папку `public` и кэш в `.cache`.

После запуска команды `gatsby develop` запустится локальный сервер разработки, который будет доступен по адресу указанный в сообщении в командной строке.

> http://localhost:8000

Встроенная в браузер IDE _GraphiQL_ для просмотра и изучения данных и схем GraphQL.

> http://localhost:8000/___graphql

#### Создание сайта и Gatsby Starters

Для создания сайта используется команда `gatsby new`, запускающая интерактивную подсказку после заполнения которой, Gatsby использует ответы для автоматического создания нового сайта на Gatsby.

```console
gatsby new my-new-site
```

или

```console
npx gatsby new my-new-site
```

_Перейти в директорию созданного сайта_

```bash
cd my-new-site
```

Для более быстрого создания сайта и запуска разработки существуют заранее разработанные и поддерживаемые сообществом готовые шаблоны сайтов Gatsby, которые называются _стартерами_ (Gatsby Starters).

Установка сайта с клонированием стартера:

```console
gatsby new [ПАПКА_САЙТА] [ССЫЛКА_НА_GIT_РЕПОЗИТОРИЙ_СТАРТЕРА]
```

Например, создадим сайт в папке `blog` со стартером `gatsby-starter-hello-world`:

```console
gatsby new blog https://github.com/gatsbyjs/gatsby-starter-hello-world
```

Подробнее о том как использовать стартеры в документации [Gatsby Starters](https://www.gatsbyjs.com/docs/starters/). Весь список стартеров доступен на [странице библиотеки Gatsby стартеров](https://www.gatsbyjs.com/starters/).

### Шпаргалка по основным командам Gatsby

![Gatsby Cheat Sheet Page 1](https://www.gatsbyjs.com/cheat-sheet_page_1.png)
![Gatsby Cheat Sheet Page 2](https://www.gatsbyjs.com/cheat-sheet_page_2.png)

### Настройка GitHub репозитория для Gatsby сайта

Многие платформы работающие с Gatsby подгружают файлы сайта с публичных репозиториев кода. На примере GitHub пример подключения удалённого репозитория:

```console
git remote add origin https://github.com/GITHUB_USERNAME/REPO_NAME.git
git branch -M master
git push -u origin master
```

## Структура Gatsby сайта

Обычная структура страниц в Gatsby выглядит следующим образом.

```text
/
|-- /.cache
|-- /plugins
|-- /public
|-- /src
    |-- /api
    |-- /pages
    |-- /templates
    |-- html.js
|-- /static
|-- gatsby-config.js
|-- gatsby-node.js
|-- gatsby-ssr.js
|-- gatsby-browser.js
```

### Папки

* `/cache` – автоматически генерируемая папка содержащая внутренний кэш в Gatsby. Содержимое не предназначено для изменения и должно быть проигнорировано в `.gitignore`;
* `/plugins` – плагины конкретного проекта на Gatsby не опубликованные как `npm` пакеты;
* `/public` – файлы проекта собранные в результате сборки, игнорируется в `gitigonre`;
* `/src` – исходные файлы проекта.
  * `/api` – зарезервированная директория файлы `*.js` и `*.ts` которых, становятся функциями Gatsby с путями основанными на имени файлов;
  * `/pages` – страницы Gatsby сайта с путями основанными на имени файлов;
  * `/templates` – шаблоны для формирования будущих страниц;
  * `html.js` – пользовательская конфигурация файла по умолчанию `.cache/default_html.js`.
* `/static` – папка для статических файлов не требующие обработки Webpack. Файлы этой папки будут скопированы в `/public` без изменений.

### Файлы

* `gatsby-browser.js` – файл описывающий использование браузерного API Gatsby (Gatsby Browser APIs) для реагирования на события в браузере;
* `gatsby-config.js` – основной файл конфигурации Gatsby. Содержит основную информацию о сайте, его метаданные, например название и описание сайта, используемые плагины и пр.;
* `gatsby-node.js` – файл описывающий использование Gatsby Node API. Код в этом файле запускается единожды при сборке сайта и позволяет динамически добавлять данные или реагировать на события во время жизненного цикла сборки сайта;
* `gatsby-ssr.js` – файл описывающий использование Gatsby Server Rendering API, позволяющий настраивать параметры и изменять содержимое статических HTML-файлов при их обработке на стороне сервера (SSR).

Поскольку сайты Gatsby также являются приложениями React, обычно используются стандартные шаблоны организации кода React, где внутри папки `/src` находятся папки типа `/components` и `/utils`.

## Создание страниц в Gatsby

Поскольку Gatsby в основе своей использует React, то элементы интерфейса и сами страницы создаются с помощью React компонентов.

_React компонент_ – это JavaScript-функция, возвращающая элемент React. Сам же _React элемент_ – это объект, который React использует для рендеринга DOM элементов.

Есть два основных типов компонентов используемые в сайтах на Gatsby:

_Компонент интерфейса_ представляет собой реализацию определённого блока в интерфейсе страницы, который может быть использован многократно.

_Компонент страницы_ содержит все элементы пользовательского интерфейса для определённой страницы сайта.

**Главная страница**

Создадим главный индексный файл `/src/pages/index.js`:

```js
// Шаг 1: Импорт библиотеки React
import React from 'react'

// Шаг 2: Определение компонента страницы
const IndexPage = () => {
  return (
    <main>
      <h1>Привет, мир!</h1>
      <p>Добро пожаловать в мой первый сайт на Gatsby!</p>
    </main>
  )
}

// Step 3: Экспорт компонента страницы
export default IndexPage
```

**Страница «Обо мне»**

Создадим ещё одну страницу «О нас» `src/pages/about.js`:

```js
import React from 'react'

const AboutPage = () => {
  return (
    <main>
      <h1>Обо мне</h1>
      <p>Всем привет! Я создатель данного сайта на Gatsby.</p>
    </main>
  )
}

export default AboutPage
```

Страницы, созданные в папке `src/pages`, используют имя файла в качестве маршрута для страницы. Например, если в папке есть файл с названием `src/pages/about.js`, то путь к этой странице будет по адресу `localhost:8000/about`.

## Добавление метаданных

Для добавления заголовка страницы `<title>` и других метаданных используется [Gatsby Head API](https://www.gatsbyjs.com/docs/reference/built-in-components/gatsby-head/). Для этого нужно экспортировать компонент с названием `Head` на странице или в шаблоне страницы.

```js
export const Head = () => <title>Главная страница</title>
```

Передача нескольких метаданных оборачивается в React Fragment.

```js
export const Head = () => (
  <>
    <title>Обо мне</title>
    <meta name="description" content="Страница обо мне" />
  </>
)
```

## Ссылки на страницы. Компонент &lt;Link&gt;

Gatsby предоставляет встроенный компонент `<Link>` для внутренних ссылок. В отличие от тега `<a>` данный компонент добавляет функционал производительности, предварительно подгружая ресурсы страницы при прокрутке ссылки или при наведении на нее указателя мыши. Это позволяет быстрее загружать страницы, когда пользователь переходит по ссылке.

Импортируйте компонент `<link>` из пакета Gatsby:

```js
import { Link } from 'gatsby'
```

Путь ссылки указывается в ~~атрибуте~~ свойстве `to=""`

```js
<Link to="/about">Обо мне</Link>
```

Для внешних ссылок, используйте обычный HTML-тег `<a>`.

## Общие компоненты страницы

На каждой странице, как правило, есть повторяющиеся части интерфейса, будь то заголовок сайта или навигация. Эти элементы можно постоянно копировать на каждую создаваемую страницу. Но что если на сайте десятки (или даже тысячи) страниц. Если понадобится внести изменения в структуру одного из блока, то это придется сделать в каждом файле по отдельности.

Повторно используемые компоненты позволяют один раз определить структуру блока интерфейса и не дублировать код каждый раз. Поскольку такие компоненты не являются компонентами определяющие саму страницу, а лишь её частью, их создают в отельной папке `/src/components`. Название папки и компонентов может быть любым.

Создадим компонент верхней (header) и нижней (footer) части страницы.

`/src/components/header.js`:

```js
import React from 'react'

const Header = () => {
  return (
    <header>
      <h1>Добро пожаловать на сайт!</h1>
      <nav>
        <ul>
          <li><Link to="/">Главная</Link></li>
          <li><Link to="/about">Обо мне</Link></li>
        </ul>
      </nav>
    </header>
  )
}

export default Header
```

`/src/components/footer.js`:

```js
import React from 'react'

const Footer = () => {
  return (
    <footer>
      <p>&copy; 2025 | Создано мной на Gatsby</p>
    </footer>
  )
}

export default Footer
```

Далее, созданные компоненты уже могут быть импортированы и использованы на страницах сайта.

```js
import React from 'react'

import Header from '../components/header'
import Footer from '../components/footer'

const IndexPage = () => {
  return (
    <div>
      <Header/>
      <main>
        <h1>Привет, мир!</h1>
        <p>Добро пожаловать в мой первый сайт на Gatsby!</p>
      </main>
      <Footer/>
    </div>
  )
}

export default IndexPage
```

## Создание макета страниц. Шаблон &lt;Layout&gt;

Разбитые на части компоненты интерфейса всё ещё вынуждают нас указывать их в каждом создаваемом файле страницы. Чтобы иметь на руках структуру всей страницы, создаётся компонент, который сгруппирует все общие повторно используемые компоненты. Это позволит вносить изменения в одном месте, когда это потребуется, чтобы применить правки ко всем страницам, использующие этот компонент.

Создадим такой компонент в `/src/components/layout.js`. Все общие компоненты, такие как `Header` и `Footer` теперь находятся в этом макете, а уникальные данные каждой страницы передаются посредством React свойства `children`.

```js
import React from 'react'

import Header from '../components/header'
import Footer from '../components/footer'

const Layout = ({ children }) => {
  return (
    <div>
      <Header/>
      <main>
        {children}
      </main>
      <Footer/>
    </div>
  )
}

export default Layout
```

Применение шаблона для главной страницы.

```js
import React from 'react'

import Layout from '../components/layout'

const IndexPage = () => {
  return (
    <Layout>
      <h1>Привет, мир!</h1>
      <p>Добро пожаловать в мой первый сайт на Gatsby!</p>
    </Layout>
  )
}

export default IndexPage
```

## Стилизация компонентов

Для стилизации страницы достаточно импортировать файл стилей на страницу.

`/src/styles/index.css`

```css
p {
  color: #333;
  font-size: 18px;
}
```

Импортируем стили для страницы «Обо мне» `/src/pages/about.js`

```js
import '../styles/index.css'
```

Стили применятся, но минус такого подхода в том, что правила распространятся не только к данному компоненту, но и абсолютно на все страницы сайта. Даже если придерживаться определённого соглашения по именованию классов, который бы разделял назначение стилей для определённых блоков интерфейса, например, правила в `.header-link` строго для ссылок в блоке `header`, такой подход всё ещё остаётся не идеальным.

## Стилизация с помощью CSS модулей

Gatsby не строго следит за тем, какой подход в стилизации вы используете. Gatsby по умолчанию поддерживает _CSS модули_ – это когда стили разбиты на модули (файлы) и привязаны к определённым компонентам во избежание конфликтов имён классов.

В папке `/src/styles/` создадим первый CSS модуль для стилизации главной страницы. Расширение `.module.css` говорит Gatsby о том, что файл должен обрабатываться как модуль CSS, а не как обычный CSS.

`/src/styles/layout.module.css`

```css
h1 {
  color: darkblue;
  font-size: 28px;
  text-align: center;
}

p {
  color: cornflowerblue;
}
```

После, импортируем его в файл шаблона `Layout` и назначим необходимым элементам через свойство `className`.

```js
import * as styles from '../styles/layout.module.css'

...

<Layout>
  <h1 className={styles.h1}>Привет, мир!</h1>
  <p className={styles.p}>Добро пожаловать в мой сайт на Gatsby!</p>
<Layout/>
```

CSS-модули сгенерирует уникальные имена классов с привязкой к именам компонентов `название-файла--селектор-класса--случайные-символы`. Это гарантирует нам, что элементы из разных компонентов будут иметь разные названия классов несмотря на то, что используют один и тот же селектор класса.

### Добавление поддержки Sass/SCSS

Плагин `gatsby-plugin-sass` обеспечивает встраиваемую поддержку Sass/SCSS.

_Установка плагина_

```console
npm install sass gatsby-plugin-sass
```

_Подключение и настройка_

Для того чтобы Gatsby смог использовать этот плагин его нужно подключить и при необходимости настроить в файле конфигурации `gatsby-config.js`, который находится в корне сайта. Описание дополнительных опций настроек в [документации плагина](https://www.gatsbyjs.com/plugins/gatsby-plugin-sass/).

```js
module.exports = {
  plugins: [
    'gatsby-plugin-sass'
  ]
}
```

После перезапуска сборки сайта `npm run develop` Gatsby начнёт поддержку плагина.

_Использование_

В файле `/src/styles/layout.scss` опишем наши стили.

```scss
$color: crimson

h1 {
  color: $color;
}
```

На главной странице `/src/pages/index.js` импортируем и применим стили к элементам.

```js
import * as styles from './layout.module.scss'

...

<h1 className={styles.h1}>Привет, мир!</h1>
```

## Работа с GraphQL

Gatsby может получать данные из одного или нескольких источников, среди которых может быть папка в файловой системе, CMS (WordPress, Drupal, Shopify, ...) или база данных.

Gatsby имеет свой собственный слой данных GraphQL где хранит все данные сайта. Посредством специальных плагинов `gatsby-source-...` добавляется возможность связи с определённым источником. Плагин извлекает данные источника и добавляет их в слой данных GraphQL вашего сайта.

![](https://www.gatsbyjs.com/static/e45422900475b86807bc002fb6863b85/10d53/data-layer.png)

### Использование инструмента GraphiQL

При запуске локального сервера разработки `gatsby develop` Gatsby позволяет использовать встроенную IDE _GraphiQL_ для исследования данных сайта и создания GraphQL-запросов. Инструмент доступен по адресу `http://localhost:8000/___graphql`.

В файле `gatsby-config.js` доступна информация о сайте в объекте `siteMetadata`. Для её получения не требуется никакого `gatsby-source-*` плагина, данные доступны в собственном слое данных GraphQL.

`gatsby-config.js`

```js
module.exports = {
  siteMetadata: {
    title: 'The Great Gatsby Site',
    description: 'My very first Gatsby site',
    author: 'Me',
  }
}
```

_GraphQL-запрос_

```graphql
{
  site {
    siteMetadata {
      author
      description
      title
    }
  }
}
```

_Ответ_

```json
{
  "data": {
    "site": {
      "siteMetadata": {
        "author": "Me",
        "description": "My very first Gatsby site",
        "title": "The Great Gatsby Site"
      }
    }
  }
}
```

### Подключение GraphQL Playground

_GraphQL Playground_ – альтернативный интерфейс IDE для создания, редактирования и тестирования GraphQL-запросов. Чтобы переключить стандартную IDE _GraphiQL_ на _GraphQL Playground_, нужно назначить специальное значение для переменной окружения. Создадим в корне проекта файл `.env.development` в котором укажем следующее значение в формате `KEY=value`:

```ini
GATSBY_GRAPHQL_IDE=playground
```

Для чтения и выполнения команд из `.env` файла установим программу `env-cmd`.

```console
npm install env-cmd --save-dev
```

Для загрузки файла с переменными окружения непосредственно перед запуском сервера разработки изменим скрипт `develop` в `package.json`.

```json
{
  "scripts": {
    "develop": "env-cmd -f .env.development gatsby develop"
  }
}
```

После перезапуска сервера `npm run develop` интерфейс IDE изменится после обновления страницы `http://localhost:8000/___graphql`.

### Запросы в базовый компонент-конструктор. Использование useStaticQuery

Базовые компоненты-конструкторы (building-block components) используются для создания более сложных компонентов и интерфейсов страниц. Запрос данных для такого компонента осуществляется через предопределённую функцию-хук `useStaticQuery` куда передаётся теговый шаблон `graphql` со строкой запроса GraphQL.

`/components/header.js`

```js
import React from 'react'
import { useStaticQuery, graphql } from 'gatsby'

const Header = () => {
  const data = useStaticQuery(graphql`
    query {
      site {
        siteMetadata {
          title
        }
      }
    }
  `)

  return (
    <header>
      <h1>{data.site.siteMetadata.title}</h1>
    </header>
  )
}

export default Header
```

`useStaticQuery` можно вызывать один раз для каждого файла. Для выборки данных из нескольких полей следует объединить их в один запрос.

```js
const data = useStaticQuery(graphql`
  query {
    site {
      siteMetadata {
        title
      }
    }
    siteBuildMetadata {
      buildTime
    }
  }
`)
```

### Запросы в компонентах страницы. Работа с файловой системой

Компоненты страницы (page components) отвечают за структуру и внешний вид всей страницы, навигацию между страницами, а также обработку событий, которые связаны с пользовательским интерфейсом.

Создадим такой компонент страницы в файле `/src/pages/blog.js`, куда выведем список всех опубликованных постов.

```js
import React from 'react'
import Layout from '../components/layout'

const BlogPage = () => {
  return (
    <Layout>
      <h1>Blog</h1>
      <p>List of posts will go in here</p>
    </Layout>
  )
}

export default BlogPage
```

Сами файлы постов в формате MDX создадим в папке `/src/posts/` с произвольным названием.

```text
. 
└─ src
   └─ posts
      ├─ blog-post-1.mdx
      ├─ blog-post-2.mdx
      └─ blog-post-3.mdx
```

### Составление запроса и выборка данных. Плагин gatsby-source-filesystem

Для получения данных из файловой системы в фреймворке Gatsby используется плагин `gatsby-source-filesystem`. Для его установки и настройки необходимо добавить его в конфигурацию проекта, а затем использовать GraphQL для запроса контента. Первым шагом будет указание плагина в объекте `plugins` в файле `gatsby-config.js`:

```js
plugins: [
  {
    resolve: 'gatsby-source-filesystem',
    options: {
      name: 'posts',
      path: `${__dirname}/src/posts/`,
    },
  },
]
```

Затем можно использовать GraphQL для запроса информации из файловой системы. Например, для получения списка всех файлов в папке `/src/posts/` можно воспользоваться следующим запросом:

```graphql
{
  allFile {
    edges {
      node {
        dir
        extension
        name
        publicURL
      }
    }
  }
}
```

## Создание страниц сайта

Описанный ранее плагин `gatsby-source-filesystem` позволял получать данные о файлах, но не о самом содержимом этих файлов. Чтобы добраться до контента этих файлов, используются трансформирующие плагины (transformer plugin). Один из

`gatsby-node.js` конфигурационный файл Node.js позволяющий нам подключится ко всевозможным API Node.js, которые предоставляет Gatsby.

### Генерация ссылок на публикации. API onCreateNode

Термин _«слаг»_ (англ. _"slug"_) относится к последней части URL и определяет уникальную строку, как правило, понятную для человека и служит для обращения к какому-либо ресурсу.

Для его динамической генерации воспользуемся конфигурационным файлом `gatsby-node.js` позволяющий нам подключится ко [всевозможным API Node.js](https://www.gatsbyjs.com/docs/reference/config-files/gatsby-node/), что предоставляет Gatsby. В нём опишем поведение для API `onCreateNode`, в котором назначим _slug_ для всех создаваемых страниц.

```js
module.exports.onCreateNode = ({ node, actions }) => {
  const { createNodeField } = actions
  if (node.internal.type === 'MarkdownRemark') {
    const slug = path.basename(node.fileAbsolutePath, '.md')
    createNodeField({
      node,
      name: 'slug',
      value: slug
    })
  }
}
```

В скрипте выше мы фильтруем только те узлы, тип которых `MarkdownRemark`, затем через встроенный модуль Node.js `path` разбираем значение поля `fileAbsolutePath`, содержащий абсолютный путь к файлу поста и получаем через `path.basename()` только имя, обрезав расширение `.md`.

Благодаря `createNodeField` _slug_ для нашей публикации будет доступен в слое данных GraphQL.

### Генерация новой страницы для каждой публикации. API createPages

Для этой задачи нам понадобится воспользоваться Gatsby Node API `createPages`, который предоставляет всё необходимое для динамической генерации новых страниц сайта.

`gatsby-node.js`

```js
module.exports.createPages = async ({  graphql, actions }) => {
  const { createPage } = actions
  // Получение пути к шаблону
  const blogTemplate = path.resolve('./src/templates/blog.js')
  // Запрос полей slug публикаций
  const response = await graphql(`
    query {
      allMarkdownRemark {
        edges {
          node {
            fields {
              slug
            }
          }
        }
      }
    }
  `)

  // Добавление данных в контекст при создании каждой новой страницы
  response.data.allMarkdownRemark.edges.forEach((edge) => {
    createPage({
      component: blogTemplate,
      path: `/blog/${edge.node.fields.slug}`,
      context: {
        slug: edge.node.fields.slug
      }
    })
  })
}
```

Переданные данные отобразятся в шаблоне который мы создадим далее. Доступ к этим дополнительным данным будет осуществлён по запросу из страницы публикации.

### Трансформация данных. Плагин gatsby-transformer-remark

Плагин `gatsby-transformer-remark` используется для преобразования Markdown-файлов в структурированные данные, которые затем могут быть использованы для динамического построения страниц в Gatsby. Плагин не требует дополнительных настроек конфигурации в `gatsby-config.js`.

После установки и перезапуске сборки проекта в слое данных GraphQL появятся запросы `MarkdownRemark` (для отдельного файла) и `allMarkdownRemark` (дя списка файлов). Готовая страница со всеми необходимыми запросами может выглядеть так:

```js
import React from 'react'
import { Link, graphql, useStaticQuery } from 'gatsby'

import Layout from '../components/layout'
import * as styles from './blog.module.scss'

const BlogPage = () => {
  const data = useStaticQuery(graphql`
    query {
      allMarkdownRemark {
        edges {
          node {
            frontmatter {
              title
              date
            }
            fields {
              slug
            }
          }
        }
      }
    }
  `)

  const li = data.allMarkdownRemark.edges.map((item, k) => {
    return (
      <li className={styles.post} key={k}>
        <h2>
          <Link to={item.node.fields.slug}>{item.node.frontmatter.title}</Link>
        </h2>
        <p>{item.node.frontmatter.date}</p>
      </li>
    )
  })

  return (
    <Layout>
      <h1>Blog</h1>

      <ol className={styles.posts}>
        {li}
      </ol>

    </Layout>
  )
}

export default BlogPage
```

### Создание шаблона страницы публикации

Создадим отдельный шаблон для будущих страниц, а чтобы компонент шаблона не путать с другими стандартными компонентами, заведём его в папке `/src/templates/`.

Поскольку мы запрашиваем данные поста ориентируясь по его _slug_, мы заводим переменную запроса (Query Variable), которая указывается сразу после ключевого слова `query`.

```graphql
query ($slug: String!) {
  ...
}
```

Gatsby сам подставит значение _slug_ в качестве аргумента в GraphQL-запросе `( fields: { slug: { eq: $slug } })`.

`/src/templates/blog.js`

```js
import React from 'react'
import { graphql } from 'gatsby'

import Layout from '../components/layout'

export const query = graphql`
  query ($slug: String!) {
    markdownRemark ( fields: { slug: { eq: $slug } }) {
      frontmatter {
        title
        date
      }
      html
      fields {
        slug
      }
    }
  }
`

const Blog = ({ data }) => {
  return (
    <Layout>
      <h1>{data.markdownRemark.frontmatter.title}</h1>
      <p>{data.markdownRemark.frontmatter.date}</p>
      <div dangerouslySetInnerHTML={{ __html: data.markdownRemark.html }}></div>
    </Layout>
  )
}

export default Blog
```

Далее, мы экспортируем GraphQL-запрос, чтобы получить доступ к его результатам в свойстве компонента шаблона `Blog`. Этот компонент отобразит нам готовую страницу публикации.

### Добавление изображений к постам

Для добавления возможности использования изображений в наших постах понадобиться установить и настроить три новых Gatsby плагинов.

Сохраним перед этим необходимые изображения в той же папке, где и будут находиться наши файлы постов, например, в папке `/src/posts/`. Подключим изображения в тексте публикации.

```markdown
---
title: "My 1st post"
date: 2025-01-15
---

Welcome to the first posts of this blog.

![A Cow on the Background of Mountains](./cow.jpg)

## Topics Covered

1. Components
2. GraphQL
3. Images
4. Plugins, Themes, & Starters
5. Data Fetching
```

По умолчанию Gatsby не знает откуда вы пытаетесь извлечь файлы картинок. Для этого понадобиться установить и настроить плагин, который бы смог обрабатывать Markdown-синтаксис вставки изображений в наших постах.

* `gatsby-plugin-sharp` – этот плагин позволяет обрабатывать изображения на базе библиотеки Sharp. Как правило, не используется напрямую, а выступает вспомогательным плагином для других плагинов;

* `gatsby-remark-images` – позволяет обрабатывать Markdown-синтаксис, где были вставлены изображения;

* `gatsby-remark-relative-images` – преобразует источники (src) изображений в `markdown/html/frontmatter` так, чтобы они были относительными к родительскому каталогу узла. Это поможет `gatsby-remark-images` находить изображения вне папки узла.

Окончательные настройки плагинов для картинок в `gatsby-config.js` могут выглядеть так:

```js
module.exports = {
  siteMetadata: {
    title: 'The Great Gatsby Site',
    description: 'My very first Gatsby site',
    author: 'Me',
  },
  plugins: [
    'gatsby-plugin-image',
    'gatsby-plugin-sass',
    {
      resolve: 'gatsby-source-filesystem',
      options: {
        name: 'src',
        path: `${__dirname}/src/`
      }
    },
    'gatsby-plugin-sharp',
    {
      resolve: 'gatsby-transformer-remark',
      options: {
        plugins: [
          'gatsby-remark-relative-images',
          {
            resolve: 'gatsby-remark-images',
            options: {
              maxWidth: 750,
              linkImagesToOriginal: false
            }
          }
        ]
      }
    }
  ],
}
```

Параметр `maxWidth` плагина `gatsby-remark-relative-images` отвечает за максимальную ширину контейнера, в котором будет помещено изображение;

`linkImagesToOriginal` добавит ссылку на исходное изображение, когда по клику отобразится полноразмерная картинка.

### Страница 404

Gatsby автоматически создает страницы из файлов каталога `src/pages`, но если пользователь переходит по несуществующему адресу, Gatsby вместо этого будет использовать компонент страницы `src/pages/404.js` для отображения ошибки.

Для создания страницы 404 всё что необходимо сделать – это создать страницу с одноимённым названием в `/src/pages/404.js`. В этой странице мы экспортируем React-компонент, что отобразит необходимые данные, когда пользователь посетит не существующую страницу.

В шаблоне мы по прежнему хотим оставить навигацию по сайту, по этой причине импортируем шаблон `Layout`, а уже внутри него отобразим необходимую информацию о странице.

`404.js`

```js
import React from 'react'

import { Link } from 'gatsby'
import Layout from '../components/layout'
import Head from '../components/head'

const NotFound = () => {
  return (
    <Layout>
      <Head title="Not Found"/>
      <h1>Page Not Found</h1>
      <p><Link to="/">Head Home</Link></p>
    </Layout>
  )
}

export default NotFound
```

В _production_ версии сборки сайта, если пользователь зайдёт на страницу, которая не была найдена, ему немедленно отобразится данный шаблон `404.js`.

## Gatsby + Contentful

_Contentful_ – это облачная, безголовая (headless) система управления контентом (CMS). Contentful + Gatsby одна из популярных связок в построении сайтов с задействованием этих двух инструментов и рассматриваемый здесь способ их использования применим с теми же принципами и к другим CMS.

В бесплатной версии аккаунта пользователю доступен лимит в 25 000 записей для публикаций (файлы изображений считаются отдельно, 1 файл = 1 запись), две локали для мультиязычного сайта, 48 видов типа контента, 2 роли прав пользователей (администратор и редактор).

После регистрации аккаунта в системе Contentful, создания там рабочего пространства (Space), нам откроется рабочий интерфейс CMS. Основные вкладки системы всего три:

* Content model – описывает модель (структуру) будущего элемента контента, определяет поля, которые будут задействованы при создании записи (заголовок, дата, тело текста, ...);
* Content – список экземпляров этого контента;
* Media – медиафайлы.

После оформления модели для публикаций, а также добавления самих записей публикаций, всё что остаётся сделать – получить доступ к этим данным через Gatsby GraphQL API.

### Установка и настройка окружения. Плагин gatsby-source-contentful

Плагин `gatsby-source-contentful` позволяет Contentful стать источником данных для Gatsby проекта.

**Установка плагина**

```shell
npm install gatsby-source-contentful gatsby-plugin-image
```

**Настройка плагина**

Всё, что необходимо сделать это указать в конфигурационном файле `gatsby-config.js` такие поля как `spaceId` и `accessToken`, который предоставляет Contentful, если в интерфейсе программы пройти в `Settings` => `API keys`.

Воспользуемся переменными окружения, чтобы скрыть чувствительные данные из исходного кода. В корне проекта в файле `*.env` создадим [переменные окружения](https://www.gatsbyjs.com/docs/how-to/local-development/environment-variables/) для описанных выше полей с произвольным названием, чтобы затем указать их в конфигурационном файле.

```js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-source-contentful`,
      options: {
        spaceId: process.env.CONTENTFUL_SPACE_ID,
        accessToken: process.env.CONTENTFUL_ACCESS_TOKEN
      },
    },
    `gatsby-plugin-image`,
  ],
}
```

### Запрос данных из источника Contentful

После перезапуска сборки в слое данных GraphQL появятся новые запросы для Contentful. Если название модели контента вы дали, например `BlogPost`, то названия запросов для данного типа контента будут соответственно `contentfulBlogPost` – для запроса данных одного отдельного поста и `allContentfulBlogPost` – для получения списка постов.

Пример запроса на извлечения списка публикаций из CMS Contentful:

```graphql
query {
  allContentfulBlogPost (
    sort: {
      fields: publishedDate,
      order: DESC
    }
  ) {
    edges {
      node {
        title
        slug
        publishedDate(formatString: "MMMM Do, YYYY")
      }
    }
  }
}
```

### Вывод списка постов. Запрос allContentfulBlogPost

Чтобы вывести списком заголовки всех публикаций в Contentful воспользуемся запросом `allContentfulBlogPost`. В IDE GraphiQL выберем поля `title`, `slug` и `publishedDate`. Последний отвечает за дату публикации, который мы можем представить в любом формате. Аргумент `formatString` позволяет форматировать вывод даты согласно шаблону библиотеки [Moment.js](https://momentjs.com/docs/#/displaying/).

Сами посты отсортируем `sort` по дате публикации `publishedDate` от поздних к ранним `DESC`.

```graphql
query {
  allContentfulBlogPost(sort: {publishedDate: DESC}) {
    edges {
      node {
        publishedDate(formatString: "MMMM Do, YYYY")
        slug
        title
      }
    }
  }
}
```

Теперь, когда у нас готов запрос, выведем этот список постов на странице `/src/pages/blog.js`. Готовый код страницы может выглядеть так:

```js
import React from 'react'
import { Link, graphql, useStaticQuery } from 'gatsby'

import Layout from '../components/layout'
import Head from '../components/head'
import * as styles from './blog.module.scss'

const BlogPage = () => {
  const data = useStaticQuery(graphql`
    query {
      allContentfulBlogPost (
        sort: {
          fields: publishedDate,
          order: DESC
        }
      ) {
        edges {
          node {
            title
            slug
            publishedDate(formatString: "MMMM Do, YYYY")
          }
        }
      }
    }
  `)

  const li = data.allContentfulBlogPost.edges.map((item, k) => {
    return (
      <li className={styles.post} key={k}>
        <h2><Link to={item.node.slug}>{item.node.title}</Link></h2>
        <p>{item.node.publishedDate}</p>
      </li>
    )
  })

  return (
    <Layout>
      <Head title="Blog" />
      <h1>Blog</h1>

      <ol className={styles.posts}>
        {li}
      </ol>

    </Layout>
  )
}

export default BlogPage
```

### Рендеринг публикации на странице. Запрос contentfulBlogPost

В этом разделе нам предстоит разобрать как динамически создавать страницы Gatsby на основе данных Contentful из ссылок, которые ведут со страницы `/src/pages/blog.js`.

В реализации этой задачи нам понадобится задействовать API `createPages` в файле `gatsby-node.js`. Поскольку ссылки на страницы генерируются самим Contentful, то здесь нам не понадобится API `onCreateNode`, как это было необходимо в работе с источником данных из файловой системы.

Чтобы получить список из `slug` наших публикаций воспользуемся GraphQL запросом `allContentfulBlogPost`.

`gatsby-node.js`

```js
const path = require('path')

module.exports.createPages = async ({ actions, graphql }) => {
  const { createPage } = actions
  const blogTemplate = path.resolve('./src/templates/blog.js')

  const response = await graphql(`
    query {
      allContentfulBlogPost {
        edges {
          node {
            slug
          }
        }
      }
    }
  `)

  response.data.allContentfulBlogPost.edges.forEach((edge) => {
    createPage({
      component: blogTemplate,
      path: `/blog/${edge.node.slug}`,
      context: {
        slug: edge.node.slug
      }
    })
  })
}
```

В файле `/src/templates/blog.js` отвечающий за вывод публикации сформируем GraphQL запрос используя `contentfulBlogPost`. В качестве аргумента запрос будет принимать параметр `slug`, для выборки конкретного поста.

Вывод таких простых полей как заголовок и дата публикации не вызывает вопросов, но что касается текста публикации `body`, то это более сложная структура, которая потребует обработки библиотекой `@contentful/rich-text-react-renderer`. Данный NPM-пакет предоставляет единственную функцию `documentToReactComponents()`, которая преобразует JSON-формат текста публикации на набор React компонентов, готовые для отображения в любом месте страницы.

```js
import React from 'react'
import { graphql } from 'gatsby'
import { GatsbyImage } from 'gatsby-plugin-image'
import { documentToReactComponents } from "@contentful/rich-text-react-renderer"
import { BLOCKS } from "@contentful/rich-text-types"

import Layout from '../components/layout'
import Head from '../components/head'

export const query = graphql`
  query($slug: String!) {
    contentfulBlogPost(slug: {eq: $slug}) {
      title
      publishedDate(formatString: "MMMM Do, YYYY")
      body {
        raw
        references {
          contentful_id
          title
          description
          gatsbyImageData(formats: [WEBP, AUTO])
        }
      }
    }
  }
`

const Blog = ({ data }) => {
  const options = {
    renderNode: {
      [BLOCKS.EMBEDDED_ASSET]: node => {
        const img = data.contentfulBlogPost.body.references.find(
          el => el.contentful_id === node.data.target.sys.id)
        return (
          <GatsbyImage
            image={img.gatsbyImageData}
            title={img.title}
            alt={img.description}
          />
        )
      }
    }
  }

  return (
    <Layout>
      <Head title={data.contentfulBlogPost.title}/>
      <h1>{data.contentfulBlogPost.title}</h1>
      <p>{data.contentfulBlogPost.publishedDate}</p>
      {documentToReactComponents(JSON.parse(data.contentfulBlogPost.body.raw), options)}
    </Layout>
  )
}

export default Blog
```

Для того чтобы отобразить картинки, нужно указать необязательный второй параметр `options` для функции `documentToReactComponents()`, в котором передать настройки отображения для встраиваемых данных, в нашем случае для изображений.

### Настройка метаданных сайта. React Helmet

_React Helmet_ – многоразовый, универсальный ~~«шлем»~~ React компонент для управления метаданными, что содержатся в секции `<head>`.

**Установка и настройка**

```shell
npm install gatsby-plugin-react-helmet react-helmet
```

В файле `gatsby-config.js` достаточно объявить использование плагина без дополнительных настроек `options`.

```js
module.exports = {
  // ...
  plugins: [
    'gatsby-plugin-react-helmet',
    // ...
  ]
}
```

**Использование**

Создадим динамический заголовок `<title>` для страниц сайта в формате `Заголовок страницы | Название сайта`. Чтобы не дублировать GraphQL-запрос для выборки нужных данных, создадим компонент `/src/components/head.js` в котором один раз реализуем необходимую логику.

```js
import React from 'react'
import { Helmet } from 'react-helmet'
import { useStaticQuery, graphql } from 'gatsby'

const Head = ({ title }) => {
  const data = useStaticQuery(graphql`
    query {
      site {
        siteMetadata {
          title
        }
      }
    }
  `)

  return <Helmet title={`${title} | ${title && data.site.siteMetadata.title}`} />
}

export default Head
```

`Заголовок страницы` будет передаваться как свойство от родительского компонента.

Вызов компонента `Head` на примере главной страницы в `/src/pages/index.js`.

```js
import React from 'react'

import Layout from '../components/layout'
import Head from '../components/head'

const IndexPage = () => {
  return (
    <Layout>
      <Head title="Home" />
      <h1>Hello, World!</h1>
      <h3>Welcome to The Great Gatsby Website</h3>
    </Layout>
  )
}

export default IndexPage
```

### Деплой сайта Gatsby

В качестве платформы для развёртывания Gatsby сайта воспользуемся [Netlify](https://netlify.com), в котором есть возможность прямой интеграции с данным фреймворком. Для этого необходимо загрузить исходный код сайта в GitHub репозиторий, из которого затем платформа Netlify будет подгружать файлы сайта и все проводимые в нём изменения.

Для начала сделаем коммит произведённых изменений перед отправкой их в удалённый репозиторий.

```console
git add .
git commit -am "Final commit"
```

Добавление удалённого репозитория и загрузка содержимого локального репозитория в удаленный.

```console
git remote add origin git@github.com:github-username/repo-name.git
git push -u origin master
```

В панели управления Netlify на вкладке `Sites` добавим новый сайт, кнопка `Add new site` => `Import an existing project`. В качестве источника данных настроим соединение с Git репозиторием провайдера GitHub. После авторизации предоставим Netlify права на чтение GitHub-репозитория проекта.

Остальные настройки можно оставить по умолчанию, за исключением настроек переменных окружения. Кликнув по кнопке `Show advanced` => `New variable` добавьте переменные окружения касающиеся CMS Contentful, что содержатся в файле `.env` в корне проекта.

Система будет автоматически забирать код с GitHub репозитория, запускать продакшн-сборку `gatsby build` и осуществлять соединение с Contentful благодаря переданным переменным окружения.

### Обновление данных сайта

Добавление новой публикации в Contentful недостаточно, чтобы она появилась на сайте. Так как мы имеем дело со статическим сайтом, его потребуется пересобрать. В панели управления Netlify на вкладке `Deploys` => кнопка `Trigger deploy` => `Clear cache and deploy site` запускает процесс пересоздания сайта после завершения которого, мы увидим сделанные изменения на сайте.

Для актуализации изменений в исходном коде нам потребуется совершить коммит изменений (`git commit`) и отправить их в удалённый репозиторий GitHub (`git push`). Netlify автоматически пересобирет проект как только произойдут изменения в ветке `master`. Запускать отдельный процесс деплоя для этого не нужно.

