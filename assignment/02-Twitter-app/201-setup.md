Previous: [200 Intro](./README.md)

# 201 Set up the new project with [vue-cli](https://github.com/vuejs/vue-cli)
>**vue-cli** is a simple CLI for scaffolding Vue.js projects. Use vue-cli as a zero-configuration development tool for your Vue apps and component, check out the [docs](https://github.com/vuejs/vue-cli/blob/dev/docs/README.md).

>Vue CLI aims to be the standard tooling baseline for the Vue ecosystem. It ensures the various build tools work smoothly together with sensible defaults so you can focus on writing your app instead of spending days wrangling with configurations. At the same time, it still offers the flexibility to tweak the config of each tool without the need for ejecting.

#### Requirements:
Node 9 is a requirement

1. Install the `vue-cli` command globally through npm:
```bash
npm install -g @vue/cli #this is beta version - bcause we are hard core 
```
2. Create a new project called `twitter-app`.
```
vue create twitter-app
```
This will trigger the installation process where you set different options for your project. You can also choose to use a js linter if you are all about the syntax-nazi..

Here's a suggested way to answer the install questions:

```bash
> Manually select features
> Select (arrows+space): CSS pre-processors and Linter / Formatter
> Select (arrows+space) your preference of pre-processor (SCSS/SASS)
> ESLint + Standard config (utan semi-colons)
> Select (arrows+space): Lint on save
> In dedicated config files
> Type: N (Save as a preset for future projects?)
```

Continue with:
```bash
cd twitter-app
yarn serve # or 'npm run serve'
```

## Explore the structure
Start exploring the structure of the project. I suggest that you start to click around and check out how the project is laid out. At least look at the following files:
- Find the `index.html`, make changes and see what happens in the browser, do you need to refresh after change?
- Find `App.vue`, make changes and see what happens in the browser, do you need to refresh after change?
- Find `HelloWorld.vue` component, make changes and see what happens in the browser, do you need to refresh after change?

# Next:
[202 List of tweets](./202-list.md)
