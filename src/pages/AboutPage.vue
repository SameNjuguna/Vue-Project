<template>
  <section class="page about">
    <h1>About Us</h1>
    <p>
      This page gives a brief overview of who we are and what we do.
      You can include your project background, goals, or inspiration here.
    </p>
  </section>
</template>

<script>
export default {
  name: "AboutPage",
};
</script>

<style>
.page {
  padding: 2rem;
  background-color: var(--bg-color);
  color: var(--text-color);
  min-height: 100vh;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.about h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}
</style>
