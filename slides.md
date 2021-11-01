---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev

background: "./images/vue-logo.png"
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Initiation à Vue 3

## Avec TypeScript et la Composition API

---

# Environmment de programmation recommandé

- Visual Studio Code pour l'éditeur de code: https://code.visualstudio.com/
- Le plugin "Volar" pour gérer le code de Vue 3: https://marketplace.visualstudio.com/items?itemName=johnsoncodehk.volar

---

# Exercice: créer un nouveau projet Vue.js 3

- Installer Vue.cli: `npm install -g @vue/cli` (ou le mettre à jour `npm update -g @vue/cli`)
- Créer un nouveau projet Vue 3: `vue create initiation-vue-3`:

  - Manually select all features:
    ✔️ Choose Vue Version
    ✔️ Babel
    ✔️ TypeScript
    ✔️ Router
    ✔️ Vuex
    ✔️ Linter/Formatter
  - Choose a version of Vue.js: <strong>3</strong>
  - Use class-style component syntax? <strong>Non</strong>
  - Use Babel alongside TypeScript: <strong>Yes</strong>
  - Pick a linter / formatter config: <strong>ESLint + Prettier</strong>
  - Pick additional lint features: **Lint on save, Lint and fix on commit**
  - Where do you prefer placing config for Babel, ESLint, etc.? **In dedicated config files**

- `cd initiation-vue 3` puis `npm run serve` pour démarrer le serveur de dev.

---

# Exemple d'Hello world avec Vue 3 et TypeScript

```vue {all|2|5|6}
<template>
  <div class="home">Hello world</div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Home",
});
</script>
```

---

# Exercice: code son premier composant - démo

<div style="padding-top:50px">
  <Counter />
</div>

---

# Exercice: coder son premier composant (1)

Ajouter une route dans le fichier `router/index.ts`

```ts
  {
    path: "/counter",
    name: "Counter",
    // route level code-splitting
    // this generates a separate chunk (about.[hash].js) for this route
    // which is lazy-loaded when the route is visited.
    component: () =>
      import(/* webpackChunkName: "counter" */ "../views/Counter.vue"),
  },
```

---

# Exercice: coder son premier composant (2)

Ajouter un lien dans le menu en éditant le fichier `App.vue`

```vue {5}
<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
    <router-link to="/counter">Counter</router-link>
  </div>
  <router-view />
</template>
```
