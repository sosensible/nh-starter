<script setup>
import { _themes as daisyThemes } from '#tailwind-config/daisyui'

const colorMode = useColorMode();

const themes = [
  "system", ...daisyThemes
];
</script>

<template>
  <div class="flex flex-col min-h-screen">
    <header class="bg-primary text-white p-4">
      <h1 class="text-2xl">My Website</h1>
      <button class="btn">Hello daisyUI</button>
      <select class="select w-full max-w-xs" v-model="colorMode.preference">
        <option disabled selected>Theme</option>
        <option v-for="theme of themes" :key="theme">{{ theme }}</option>
      </select>
    </header>
    <main class="flex-grow p-4">
      <slot />
    </main>
    <footer class="bg-primary text-white p-4 mt-auto">
      <p>&copy; 2023 My Website</p>
    </footer>
  </div>
</template>