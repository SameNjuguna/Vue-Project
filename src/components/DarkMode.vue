<template>
  <button @click="toggleTheme" class="dark-toggle">
    {{ isDark ? '☀️ Light' : '🌙 Dark' }}
  </button>
</template>

<script setup>
import { useTheme } from '../composables/useTheme.js'
const { isDark, toggleTheme } = useTheme()
</script>

<style>
.dark-toggle {
  background: none;
  border: 1px solid var(--text-color);
  color: var(--text-color);
  padding: 0.4rem 0.8rem;
  border-radius: 6px;
  cursor: pointer;
  transition: 0.3s;
}

.dark-toggle:hover {
  opacity: 0.8;
}
</style>
