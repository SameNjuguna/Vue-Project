<template>
  <section class="page home">
    <h1>Welcome to Our Vue App</h1>
    <p>
      This is the home page of your Vue class project.
      Use this section to introduce your project or brand.
    </p>
  </section>
</template>

<script>
export default {
  name: "HomePage",
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

.home h1 {
  font-size: 2rem;
  margin-bottom: 1rem;
}
</style>
