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
<div v-click ="1" >

<!-- 1st click: Progressive -->
- 📈 **Progressive** 
  - Can enhance normal HTML pages
  - Full app support
  - Modular adoption
</div>
</Transition>
<div v-click="2" >

<!-- 2nd click: JavaScript -->
- 💻 **JavaScript** 
  - Built with JavaScript
  - lets you create interactive user interfaces by writing logic in JS
  - It handles templates, reactivity, and DOM updates — all with JavaScript.
</div>
</div>

<div v-click="3" >

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

  <div v-click="1" >

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


  <div v-click="2" >

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

<div v-click="1" >

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
<div v-click="2"  >

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

# `reactive` vs `ref` in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

## Using `reactive`

```js
import { reactive } from 'vue'

const state = reactive({
  count: 0,
  message: 'Hello'
})

// Usage
state.count++
state.message = 'Hi!'
```

- `reactive` is used for making entire objects reactive (including arrays).

</div>

<div v-click="2">

## Difference between `ref` and `reactive`

- **`ref`**: Makes a single value (primitive or object) reactive.  
  Access the value with `.value`.
- **`reactive`**: Makes an entire object or array reactive.  
  Access properties directly (no `.value` needed).
- Use `ref` for primitives or when you want to wrap a single value.  
- Use `reactive` for objects with multiple properties.
</div>
</div>

---
transition: fade
clicks: 4
---

# Built-in Directives

<div grid="~ cols-2 gap-5">
<div v-click="1">

## `v-bind`
- Dynamically binds an attribute to an expression.
```html
<img v-bind:src="imageUrl" />
<!-- Shorthand: -->
<img :src="imageUrl" />
```
</div>

<div v-click="2">

## `v-text`
- Updates the element’s `textContent` with the value of an expression.
```html
<span v-text="message"></span>
<!-- Equivalent to: -->
<span>{{ message }}</span>
```
</div>

<div v-click="3">

## `v-html`
- Updates the element’s `innerHTML` with the value of an expression (renders raw HTML).
```html
<div v-html="rawHtml"></div>
```

**Caution:** Only use with trusted content.
</div>

<div v-click="4">

## `v-show`
- Conditionally shows or hides an element by toggling its CSS `display` property.
```html
<p v-show="isVisible">Is visible if isVisible is true</p>
```

</div>
</div>


---
transition: fade
clicks: 3
---

# Conditional Rendering in Vue

<div v-click="1">

### `v-if`  Renders the element only if the condition is true.
```html
<p v-if="isLoggedIn">Welcome back!</p>
```
</div>
<br>
<div v-click="2">

### `v-else` Renders the element if the previous `v-if` condition is false.
```html
<p v-if="isLoggedIn">Welcome back!</p>
<p v-else>Please log in.</p>
```
</div>
<br>
<div v-click="3">

### `v-else-if` Checks another condition if the previous `v-if` is false.
```html
<p v-if="score > 90">Excellent!</p>
<p v-else-if="score > 60">Good job!</p>
<p v-else>Keep trying!</p>
```
</div>

---
transition: fade
clicks: 1
---

# Looping

<div v-click="1">

## Using `v-for`
- `v-for` is used to render a list of items by looping over an array.

```html
<ul>
  <li v-for="item in items" :key="item.id">
    {{ item.name }}
  </li>
</ul>
```

- `:key` helps Vue efficiently update each item.



```js
import { ref } from 'vue'

const items = ref([
  { id: 1, name: 'Apple' },
  { id: 2, name: 'Banana' },
  { id: 3, name: 'Cherry' }
])
```

</div>

---
transition: fade
clicks: 2
---

# Disabling Re-render

<div v-click="1">

## Why Disable Re-render?
- Sometimes you want to prevent Vue from updating a part of the DOM, even if reactive data changes.
- Useful for static content or optimizing performance in specific cases.

</div>
<br>
<div v-click="2">

## Using `v-once`

- The `v-once` directive renders the element and component **only once** and skips future re-renders.

```html
<p v-once>This will never update: {{ count }}</p>
```

- No matter how `count` changes, the content will not update after the initial render.
</div>

---
transition: fade
clicks: 2
---

# Working with Events in Vue
<div grid="~ cols-2 gap-5">

<div v-click="1">

## Listening to Events

- Use the `v-on` directive (or `@` shorthand) to listen for DOM events.

```html
<button @click="increment">Add</button>
```

```js
import { ref } from 'vue'
const count = ref(0)
function increment() {
  count.value++
}
```

</div>

<div v-click="2">

## Passing Event Data

- You can access the event object or pass arguments:

```html
<input @input="onInput($event)" />
<button @click="sayHello('Vue')">Say Hello</button>
```

```js
function onInput(event) {
  console.log(event.target.value)
}
function sayHello(name) {
  alert(`Hello, ${name}!`)
}
```
</div>
</div>

---
transition: fade
clicks: 2
---

# Forms and `v-model` in Vue

<div v-click="1">

## Two-way Binding with `v-model`

- `v-model` creates a two-way binding between form inputs and your data.

```html
<input v-model="name" placeholder="Enter your name" />
<p>Hello, {{ name }}!</p>
```

- When the input changes, `name` updates automatically, and vice versa.

</div>
<br>
<div v-click="2">

## Example with Multiple Inputs

```html
<input v-model="email" placeholder="Email" />
<input type="checkbox" v-model="subscribe" /> Subscribe
<p>Email: {{ email }}</p>
<p>Subscribed: {{ subscribe }}</p>
```

- Works with text, checkbox, radio, select, and textarea elements.

</div>

---
transition: fade
clicks: 3
---

# Class Binding
<div grid="~ cols-2 gap-5">
<div>
<div v-click="1">

### Object Syntax

- Bind classes conditionally using an object.
- The key is the class name, the value is a boolean.

```html
<div :class="{ active: isActive, 'text-large': isLarge }">
  Object syntax example
</div>
```

</div>
<br>
<div v-click="2">

### Array Syntax

- Bind multiple classes using an array.
- Each entry can be a string or an object.

```html
<div :class="[baseClass, isActive ? 'active' : '', { 'text-large': isLarge }]">
  Array syntax example
</div>
```

</div>
</div>
<div v-click="3">

### String Syntax

- Bind a single class or multiple classes as a space-separated string.

```html
<div :class="`btn ${isPrimary ? 'btn-primary' : 'btn-secondary'}`">
  String syntax example
</div>
```
</div>
</div>

---
transition: fade
clicks: 2
---

# Style Binding

<div v-click="1">

### Object Syntax

- The key is the CSS property, the value is a variable or expression.

```html
<div :style="{ color: activeColor, fontSize: size + 'px' }">
  Object style binding example
</div>
```

</div>
<br>
<div v-click="2">

### Array & String Syntax

- Bind multiple style objects or use a string for inline styles.

```html
<div :style="[baseStyles, overrideStyles]">
  Array style binding example
</div>

<div :style="'background: yellow; color: blue;'">
  String style binding example
</div>
```

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

---
transition: fade
clicks: 2
---

# Watchers

<div v-click="1">

## What is a Watcher?

- A watcher lets you run custom code in response to changes in a reactive value or computed property.
- Useful for side effects like API calls, logging, or reacting to user input.

</div>
<br>
<div v-click="2">

## Using `watch`

```js
import { ref, watch } from 'vue'

const count = ref(0)

watch(count, (newValue, oldValue) => {
  console.log(`Count changed from ${oldValue} to ${newValue}`)
})
```

- The callback runs every time `count.value` changes.
- You can also watch multiple sources or use options like `immediate` and `deep`.

</div>

---
transition: fade
clicks: 2
---

# Registering Components in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

### 1. **Global Registration**

- Register a component globally so it can be used anywhere in your app.

```js
import { createApp } from 'vue'
import MyComponent from './MyComponent.vue'

const app = createApp(App)
app.component('MyComponent', MyComponent)
app.mount('#app')
```

</div>
<div v-click="2">

### 2. Local Registration with `<script setup>`


- In Vue 3 with `<script setup>`, just import your component and use it in the template—no need to register in a `components` option.

```vue
<script setup>
import MyComponent from './MyComponent.vue'
</script>

<template>
  <MyComponent />
</template>
```

</div>
</div>

---
transition: fade
clicks: 2
---

# Scoped Styles in Vue

<div v-click="1">

### Why Use Scoped Styles?

- By default, styles in a Vue component apply globally.
- Adding the `scoped` attribute to the `<style>` tag ensures styles only apply to that component.

</div>

<div v-click="2">
<br>

### Example

```vue
<template>
  <p class="red-text">This is red only in this component!</p>
</template>

<style scoped>
.red-text {
  color: red;
}
</style>
```

- The `.red-text` style will not affect elements in other components

</div>

---
transition: fade
clicks: 2
---

# Passing Props in Vue
<div grid="~ cols-2 gap-5">

<div v-click="1">

### Passing Props to a Component

- Use attributes to pass data from a parent to a child component.

```html
<!-- ParentComponent.vue -->
<UserCard :name="userName" :age="userAge" />
```
<br>
<br>
<br>

- Now `UserCard` receives and uses the `name` and `age` props from its parent.
</div>

<div v-click="2">

### Defining Props in the Child Component

- In the child, define props using the `defineProps` macro with `<script setup>`:

```vue
<!-- UserCard.vue -->
<script setup>
const props = defineProps({
  name: String,
  age: Number
})
</script>

<template>
  <div>
    <h2>{{ name }}</h2>
    <p>Age: {{ age }}</p>
  </div>
</template>
```
</div>
</div>

---
transition: fade
clicks: 2
---

# Emitting Events to Change Props
<div grid="~ cols-2 gap-5">

<div v-click="1">
  <div >

### Why Emit Events?

- Props are **one-way**: parent ➡️ child.
- To update a prop value, the child **emits an event** and the parent updates the value.


### Example

```vue
<!-- Child Component (`CounterButton.vue`) -->
<script setup>
const props = defineProps({ count: Number })
const emit = defineEmits(['update:count'])
function increment() {
  emit('update:count', props.count + 1)
}
</script>
<template>
  <button @click="increment">Clicked {{ count }} times</button>
</template>
```
  
  </div>
</div>

<div v-click="2">

```vue
<!-- Parent Component -->
<script setup>
import { ref } from 'vue'
import CounterButton from './CounterButton.vue'

const count = ref(0)
</script>

<template>
  <CounterButton :count="count" @update:count="count = $event" />
</template>
```

- The child emits `update:count` with the new value.
- The parent listens and updates its state.

</div>
</div>

---
transition: fade
clicks: 2
---

# Passing a Function Prop to Update Parent State
<div grid="~ cols-2 gap-5">
<div v-click="1">

- Sometimes, instead of emitting events, you can pass a function from the parent to the child.
- The child calls this function to update the parent's state directly.

```vue
<!-- Parent Component -->
<script setup>
import { ref } from 'vue'
import CounterButton from './CounterButton.vue'

const count = ref(0)
function increment() {
  count.value++
}
</script>

<template>
  <CounterButton :count="count" :onIncrement="increment" />
</template>
```
</div>

<div v-click="2">

```vue
<!-- Child Component (`CounterButton.vue`) -->
<script setup>
const props = defineProps({
  count: Number,
  onIncrement: Function
})
</script>

<template>
  <button @click="onIncrement">Clicked {{ count }} times</button>
</template>
```

- The parent passes its `increment` function as a prop.
- The child calls `onIncrement()` to update the parent's value.
</div>
</div>

---
transition: fade
clicks: 2
---

### Vue Component Lifecycles
<div grid="~ cols-2 gap-5">

<div v-click="1">

| Hook                | When it Runs                                 |
|---------------------|----------------------------------------------|
| `onBeforeMount`     | Before the component is mounted to the DOM   |
| `onMounted`         | After the component is mounted               |
| `onBeforeUpdate`    | Before reactive data causes a re-render      |
| `onUpdated`         | After the DOM is updated                     |
| `onBeforeUnmount`   | Before the component is unmounted            |
| `onUnmounted`       | After the component is unmounted             |

</div>
<div v-click="2">

### Example Usage

```vue
<script setup>
import { onMounted, onUpdated, onUnmounted } from 'vue'

onMounted(() => {
  console.log('Component mounted!')
})

onUpdated(() => {
  console.log('Component updated!')
})

onUnmounted(() => {
  console.log('Component unmounted!')
})
</script>
```

- Use these hooks to fetch data, set up timers, clean up, etc.

</div>
</div>

---
transition: fade
clicks: 2
---

# Provide & Inject in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

### What is Provide & Inject?

- `provide` and `inject` are used to share data between a parent and its descendants, skipping intermediate components.
- Useful for passing down global data like themes, user info, or configuration without prop drilling.

</div>

<div v-click="2">

### Example Usage

```vue
<!-- ParentComponent.vue -->
<script setup>
import { provide } from 'vue'
provide('theme', 'dark')
</script>
```

```vue
<!-- DeepChild.vue -->
<script setup>
import { inject } from 'vue'
const theme = inject('theme')
</script>
<template>
  <div>Current theme: {{ theme }}</div>
</template>
```

- The `theme` value is available to any descendant that calls `inject('theme')`, no matter how deep in the component tree.
</div>
</div>

---
transition: fade
clicks: 2
---

# Slots in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

## What are Slots?

- Slots allow you to pass content from a parent component into a child component.
- Useful for creating reusable and flexible components.

```html
<!-- BaseLayout.vue -->
<template>
  <header>Header</header>
  <slot></slot>
  <footer>Footer</footer>
</template>
```
</div>

<div v-click="2">

## Using Slots

```vue
<!-- ParentComponent.vue -->
<BaseLayout>
  <main>
    <h1>Hello from the parent!</h1>
  </main>
</BaseLayout>
```

- The content inside `<BaseLayout>` replaces the `<slot></slot>` in the child.
- You can also use **named slots** and **scoped slots** for more advanced use cases.
</div>
</div>

---
transition: fade
clicks: 2
---

# Working with Forms in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

- Use `v-model` to bind form input values to reactive data.

```html
<input v-model="username" placeholder="Enter your username" />
<p>Your username: {{ username }}</p>
```

- Changes in the input update `username`, and vice versa.

</div>

<div v-click="2">

#### Handling Form Submission

```vue
<script setup>
import { ref } from 'vue'
const email = ref('')
function submitForm() {
  alert(`Submitted: ${email.value}`)
}
</script>
<template>
  <form @submit.prevent="submitForm">
    <input v-model="email" placeholder="Email" />
    <button type="submit">Submit</button>
  </form>
</template>
```

- Use `@submit.prevent` to handle form submission and prevent page reload.
- Combine `v-model` with methods for full form handling.
</div>
</div>

---
transition: fade
clicks: 2
---

## Form Validation with vee-validate in Vue
<div grid="~ cols-2 gap-5">
<div v-click="1">

### What is vee-validate?

- **vee-validate** is a popular library for form validation in Vue 3.
- It provides easy-to-use validation rules and error handling for forms.


- Use `useForm` and `useField` to manage form state and validation.
- Display error messages using the `errors` object.
</div>

<div v-click="2">

```vue
<script setup>
import { useField, useForm } from 'vee-validate'
import { required, email } from '@vee-validate/rules'

const { handleSubmit, errors } = useForm()
const { value: emailValue } = useField('email', email)
const { value: nameValue } = useField('name', required)

const onSubmit = handleSubmit(values => {
  alert(JSON.stringify(values))
})
</script>

<template>
  <form @submit.prevent="onSubmit">
    <input v-model="nameValue" placeholder="Name" />
    <span>{{ errors.name }}</span>
    <input v-model="emailValue" placeholder="Email" />
    <span>{{ errors.email }}</span>
    <button type="submit">Submit</button>
  </form>
</template>
```

</div>
</div>

---
transition: fade
clicks: 2
---

## Installing and Using Vue Router
<div grid="~ cols-2 gap-5">
<div v-click="1">

**Install Vue Router**

Open your terminal in your project folder and run:

```sh
npm install vue-router@4
```

**Create a `router.js` file:**

```js
import { createRouter, createWebHistory } from 'vue-router'
import Home from './components/Home.vue'
import About from './components/About.vue'

const routes = [
  { path: '/', component: Home },
  { path: '/about', component: About }
]

export const router = createRouter({
  history: createWebHistory(),
  routes,
})
```
</div>

<div v-click="2">

**Update your `main.js`:**

```js
import { createApp } from 'vue'
import App from './App.vue'
import { router } from './router'

createApp(App).use(router).mount('#app')
```

- Now use `<router-link>` and `<router-view>` in your components to enable navigation.
</div>
</div>

---
transition: fade
clicks: 2
---

# Using `<router-link>` and `<router-view>` in Vue
<div grid="~ cols-2 gap-5">

<div v-click="1">

## Navigation with `<router-link>`

- Use `<router-link>` to create navigation links that work with Vue Router.

```html
<router-link to="/">Home</router-link>
<router-link to="/about">About</router-link>
```

- This prevents full page reloads and enables SPA navigation.

</div>

<div v-click="2">

## Displaying Route Content with `<router-view>`

- Place `<router-view>` in your main layout or App.vue to render the matched component for the current route.

```html
<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>
```

- The component for the current route will be displayed where `<router-view />` is placed.
</div>
</div>

---
transition: fade
---

### More Topics for Self-Learning
<div grid="~ cols-2 gap-5">
<div>

- **Teleport**  
  Render content outside the current component hierarchy (e.g., modals, tooltips).

- **Dynamic & Async Components**  
  Load components dynamically or asynchronously for better performance.

- **Custom Directives**  
  Create your own directives for reusable DOM behavior.

- **Mixins & Composables**  
  Reuse logic across components using mixins or the Composition API's composables.


- **Error Handling**  
  Global error boundaries and errorCaptured hook.
</div>
<div>

- **Testing Vue Apps**  
  Unit and end-to-end testing with tools like Vue Test Utils and Cypress.

- **Vuex & Pinia**  
  Advanced state management solutions.

- **Internationalization (i18n)**  
  Supporting multiple languages in your app.

- **Accessibility (a11y)**  
  Making your Vue apps accessible to all users.

- **Performance Optimization**  
  Lazy loading, code splitting, and optimizing reactivity.

> Explore the [Vue 3 documentation](https://vuejs.org/guide/introduction.html) for deep dives into these topics.
</div>
</div>
---
transition: fade
---

# Thank You!

<!-- - For the assignment, please refer to [this link](https://shreyasp-kott.github.io/Who-pays-the-bill/). -->
- Happy learning and coding with Vue! 🚀








