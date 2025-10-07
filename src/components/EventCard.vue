<template>
  <div class="event-card">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String
})
</script>

<style>
.event-card {
  border: 1px solid var(--text-color);
  border-radius: 8px;
  padding: 1rem;
  margin: 1rem 0;
  background-color: var(--bg-color);
  transition: 0.3s;
}

.event-card:hover {
  transform: translateY(-2px);
}
</style>
