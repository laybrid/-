<template>
  <router-view />
</template>

<script setup lang="ts">
import { useDarkMode } from './assets/utils/useDarkMode'
import { MoonIcon, SunIcon, ArrowDownCircleIcon } from '@heroicons/vue/24/outline'
const { modeState, changeMode } = useDarkMode()
</script>

<style>
html,
body,
#app {
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: #fce7f3;
  font-family: system-ui, Avenir, Helvetica, Arial, sans-serif;
  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #213547;
}
</style>
