---
theme: vuetiful
layout: cover
altCover: true
clicks: 1
transition: fade-out
---
# Vue.js

The Progressive JavaScript Framework

<style>
.slidev-layout {
  color: #222 !important;
}
</style>


---
clicks: 3

---

# Why is it called the Progressive JavaScript Framework?

<div grid="~ cols-2 gap-4">
<Transition name="fade">
<div v-click ="1" v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :leave="{ x: 80 }" >

<!-- 1st click: Progressive -->
- 📈 **Progressive** 
  - Can enhance normal HTML pages
  - Full app support
  - Modular adoption
</div>
</Transition>
<div v-click="2" v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :leave="{ x: 80 }">

<!-- 2nd click: JavaScript -->
- 💻 **JavaScript** 
  - Built with JavaScript
  - lets you create interactive user interfaces by writing logic in JS
  - It handles templates, reactivity, and DOM updates — all with JavaScript.
</div>
</div>

<div v-click="3" v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :leave="{ x: 80 }">

<!-- 3rd click: Framework -->
- 🛠 **Framework**  
  - More than just a utility library  
  - It gives a structured system for:
    - Components
    - Routing
    - State management
</div>
<br>
<br>


---
transition: slide-up
level: 1
---

# Popular UI Frameworks

<div class="flex justify-center items-center gap-12 mt-20">
  <div class="flex flex-col justify-center" v-click="1" v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :leave="{ x: 80 }">
    <img src="https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg" alt="React" width="220" height="120" />
    <div class="text-center mt-20">React</div>
  </div>
  <div class="flex flex-col justify-center" v-click="3" v-motion
  :initial="{ y: 80 }"
  :enter="{ y: 0 }"
  :leave="{ y: -80 }">
    <img src="https://upload.wikimedia.org/wikipedia/commons/9/95/Vue.js_Logo_2.svg" alt="Vue" width="220" height="120" />
    <div class="text-center mt-20">Vue</div>
  </div>
  <div class="flex flex-col justify-center" v-click="2" v-motion
  :initial="{ x: 80 }"
  :enter="{ x: 0 }"
  :leave="{ x: -80 }">
    <img src="https://angular.io/assets/images/logos/angular/angular.svg" alt="Angular" width="220" height="120" />
    <div class="text-center mt-13">Angular</div>
  </div>
</div>

---
transition: slide-left
---

# Counter Example: Plain JS vs Vue

<div grid="~ cols-2 gap-1">
  <div v-click="1">


  ```html {v-pre}
  <head>  
      <title>Counter Example</title>
  </head>
  <body>
    <div id="plain-app">
      <button onclick="count--; update()">Remove</button>
      <span id="plain-count">0</span>
      <button onclick="count++; update()">Add</button>
    </div>
    

  <script>
    let count = 0;
    const update = () => {
      document.getElementById('plain-count').textContent = count;
    }
    update();
  </script>

  </body>

  ```
  </div>

  <div v-click="2">

  ```html {v-pre}
  <head>
    <script src="https://unpkg.com/vue@3" ></script>
  </head>
  <body>
    <div id="vue-app">
      <button @click="count--">Remove</button>
      <span>{{ count }}</span>
      <button @click="count++">Add</button>
    </div>

  <script>
    const { createApp, ref } = Vue
    createApp({
      setup() {
        const count = ref(0)
        return { count }
      }
    }).mount('#vue-app')
  </script>
  </body>
  ```

  </div>
</div>

<style>
.slidev-vclick-target {
  transition: all 500ms ease;
}

.slidev-vclick-hidden {
  transform: scale(0);
}
</style>

---
transition: slide-down
clicks: 2
---

# Setting Up for Vue Development
<div grid="~ cols-2 gap-5">

  <div v-click="1" v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :leave="{ x: 80 }">

  ## Extensions for VS Code

  - **Vue Extension Box** 
    - IntelliSense for Vue files
    - Linting
    - Formatting the files
    - Auto-closing tags
    - Auto-renaming tags
  - **Vue VSCode Snippets**  
    Quickly scaffolds Vue components and templates.
  </div>


  <div v-click="2" v-motion :initial="{ x: -80 }" :enter="{ x: 0 }" :leave="{ x: 80 }" >

  ## Additional Tips for VS Code

  - Enable **format on save** in VS Code settings.
  - Use the **Integrated Terminal** for running `npm run dev` and other scripts.
  - Explore the **Source Control** panel for Git integration.
  
  <br/>


  ## Vue Devtools
  - Install the Vue Devtools browser extension for debugging.
  - It provides a powerful interface to inspect Vue components, state, and events.

   
  </div>
</div>

---
transition: slide-right
clicks: 2
---

# Setting Up a Vue Project from Scratch
<div grid="~ cols-2 gap-5">

<div v-click="1"  v-motion :initial="{ x: -80 }" :enter="{ x: 0 }" :leave="{ x: 80 }">

## 1. Install Node.js

- Download and install Node.js from [nodejs.org](https://nodejs.org/).

<br>

## 2. Create a New Vue Project

Open your terminal and run:

```sh
npm create vue@latest
```

- Follow the prompts to select features (choose defaults if unsure).
- This will scaffold a new Vue 3 project in a folder you specify.

</div>
<div v-click="2"  v-motion :initial="{ x: -80 }" :enter="{ x: 0 }" :leave="{ x: 80 }">

## 3. Start the Development Server

Navigate into your project folder and run:

```sh
cd your-project-name
npm install
npm run dev
```

- Open the provided local URL in your browser to see your Vue app running!
</div>
</div>

---
transition: fade
clicks: 3
---

# Reactivity in Vue

<div v-click="1">

## What is Reactivity?
- Reactivity means your UI automatically updates when your data changes.
- Vue tracks dependencies and updates only what's needed.
</div>
<br>
<div v-click="2">

## How does Vue do it?
- Vue wraps your data in special reactive objects (like `ref` or `reactive`).
- When you change a reactive value, Vue knows which parts of the DOM to update.
</div>

<div v-click="3">

## Example

```js
import { ref } from 'vue'
const count = ref(0)
count.value++ // UI updates automatically!
```
- Changing `count.value` triggers the DOM to update wherever it's used.
</div>


---
transition: fade
clicks: 2
---

# Computed Properties in Vue

<div v-click="1">

## What are Computed Properties?
- Computed properties are special values that are automatically recalculated when their dependencies change.
- They are useful for deriving new data from existing reactive state, without manual updates.

</div>
<br>
<div v-click="2">

## Example

```js
import { ref, computed } from 'vue'

const count = ref(0)
const double = computed(() => count.value * 2)

count.value++ // double.value is now 2
```
- Here, `double` will always reflect twice the value of `count`
</div>








