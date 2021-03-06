# Nuxt.js Fundamentals
Learn the fundamentals of Nuxt.js in this course that we created together with the founders of Nuxt. The course covers what you need to know from scaffolding to deploying your first Nuxt.js application.

Nuxt.js is a framework for creating Vue.js applications. Its goal is to help Vue developers take advantage of top-notch technologies and features in a fast, easy and organized way.

The course covers the fundamentals of Nuxt.js and serves as a platform for everyone who wants to get started with Nuxt.

You do not need to know Nuxt.js to take this course, but you should know Vue.js.

After this course, you will be familiar with:
- What Nuxt.js is and how it can help you and your projects
- How to scaffold new Projects with their create-nuxt-app tool
- The structure of a Nuxt application
- Creating and navigating between pages
- Setting up meta tags for improved SEO
- Building and deploying a Nuxt.js App
- How to deploy your apps to Heroku and Netlify

This course is made together with the Chopin brothers (founders of Nuxt.js) and core member Alexander Lichter.

## a. CSR and SSR

Смотри диаграмму `csr-ssr.png`.

CSR - client side rendering
1. делаем запрос к серверу
2. получаем "пустой" html, в котором ссылки на дополнительные ресурсы
3. скачиваем JS bundle (они сжатые)
4. render-им страницу и приложение
Минус: СЕО роботы не видят контент и чуть дольше грузится

SSR - server side rendering (в целом это быстрее)
1. делаем запрос к серверу
2. получаем почти готовый html, уже можно работать
3. в фоне докачиваем JS bundle (они сжатые), их меньше и грузит быстрее
4. render-им страницу и приложение, быстрее получаем приложение
Далее он работает динамически, без перезагрузки страниц.


## 1. What is Nuxt.js?

Nuxt.js is a framework for creating Vue.js applications. Its goal is to help Vue developers take advantage of top-notch technologies, fast, easy and in an organized way.

In this lesson, we talk about some of the awesome features Nuxt.js brings to the table:
- SEO with Server Side Rendering (SSR)
- Pre Rendering
- Code Splitting

Nuxt = Vue + Vue-router + Vuex

## Create Nuxt App

https://nuxtjs.org/guide/installation

Nuxt.js has an official scaffolding tool (create-nuxt-app), that you can use from your package manager.
Такой же установочный модуль есть у React.

In this lesson, we will use yarn to set up our new Nuxt.js project, with this command:
```
yarn create nuxt-app nuxt-fundamentals
```

Settings:
- Rendering Mode = Universal (= Server Side Rendering) 
- Package Manager = Yarn

You can also use npx (´npx´ is shipped by default since NPM ´5.2.0´)
```
npx -v
npx create-nuxt-app nuxt-fundamentals
```

Что такое `npx`? Это новая утилита Node.js. Из команды выше она установит глобально create-nuxt-app, потом создаст наше приложение и потом удалит create-nuxt-app.
Раньше нам надо было глобально поставить create-nuxt-app, а потом создавать приложения.

При установке можно выбрать любой серверный фреймворк.

Install Yarn `npm install -g yarn`

About Yarn:
- https://code.fb.com/web/yarn-a-new-package-manager-for-javascript/
- https://github.com/yarnpkg/yarn

Start Nuxt `yarn dev` (у меня генерируется в 1.5 раза дольше, чем на МакБук-Про - 5 сек против 3.2 сек)

## Guided Nuxt.js Project Tour

In this lesson, we'll show you around in our newly created Nuxt project.

Please note that each directory includes a readme file, that explains what the directory is. You can safely delete the directories of the features you do not need.

Обзор папок:
- `.nuxt` - системная папка
- `nuxt.config.js` - главный файл, кт конфигурирует приложение

Нет файла index.html, почему? Потому что он собирается автоматически из настроек pkg.name - берет имя из package.json

Важно! Исходники страницы уже сгенерированы (Ctrl+U) отличается от Инспектора кода (Ctrl+Shift+I) 

Давайте поменяем `universal` на `spa` в файле `nuxt.config.js` и теперь будет генерироваться только Клиент без Сервера.


- ``
- ``
- ``
- ``
- ``

## Customize the home page

In this lesson, we start to customize our home page of our Nuxt project.

Click here to get the CSS we use in the video.

## 5. Nuxt.js Page Components

In this lesson, we will learn how to create new pages in a Nuxt.js application. We also see a real-world example of why you should always use multi-worded names on your components.

- change layouts\default.vue, its like vue.app;
- add new page - pages\post.vue
- test it http://localhost:3000/post

## 6. Global CSS

While scoped styles are handy, they cannot solve all our CSS needs. You often need to have a set of global CSS rules to take care of your fundamental styling needs.

Luckily Nuxt.js has a very elegant solution that allows us to inject global CSS in our project directly from the config file. Whether it is a custom CSS file from your assets directory or an NPM package.

- add assets/style.css
- move global styles to this file
- add filepath to style.css in /nuxt.config.js
- after changes was made you have to restart server `yarn run dev`

## 7. Adding a Navbar to Nuxt Apps

In this lesson, we're exploring where to put your navbar and other parts of your application that will be present on all pages.

- add components/Navbar.vue
- add navbar to layouts/default.vue

## 8. Dynamic Routes

In this Nuxt.js lesson, we're looking into the router and dynamic routes. When we are working with dynamic content we need to pass the ID (or similar) of the content we would like to visit.

Luckily, Nuxt handles this automagically for us.

## 9. Linking Between Pages

In this lesson, we'll learn how to link between pages in Nuxt, with `nuxt-link`.

If we use regular anchor tags, the application will refresh if a user clicks a link, which is not what we want in a modern single page application.

Nuxt-link works without reloading page like `a href=`. Its benefit.

## 10. Utilising the Vuex Store

Another great feature of Nuxt.js is that it supports [Vuex](https://vuex.vuejs.org/) out of the box. In this lesson, we're learning what we need to know to work with Vuex and Nuxt.

Nuxt offer 2 modes to use Vuex:
- Modules mode (Classic);

## 11. SEO and Meta Tags

In this lesson, we're going to learn how Nuxt.js can make our JavaScript applications SEO friendly with pre-rendering and meta tags.

## 12. Build and Serve the Nuxt.js App

When our Nuxt app is ready to be deployed, we have to build our application before we can publish it on the internet. In this lesson, we're learning how to do just that.

```
yarn build
yarn start
```

## 13. How to Deploy Nuxt.js to Heroku

[Heroku](https://www.heroku.com/) is an easy and affordable service that we can use to host our Nuxt applications. In this lesson, we'll learn how to deploy our nuxt.js application to Heroku.

{Learn more about deploying your Nuxt.js app to Heroku](https://nuxtjs.org/faq/heroku-deployment/)

Lets go:
- create Heroku account;
- add App;
- install Heroku cli;

## 14. How to Deploy Nuxt.js to Netlify

A cool feature of Nuxt is that it can generate a static version of your application which you can deploy without the need of a server. This means that you can host your application in a service like Netlify or GitHub pages which are actually free even when you have a ton of traffic.

In this lesson, we're learning how to pre-render our application and deploying it to Netlify. Pre-rendering makes our application load faster, it improves SEO and can actually reduce our hosting costs drastically.

