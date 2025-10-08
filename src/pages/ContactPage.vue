<template>
  <section class="page contact">
    <h1>Contact Us</h1>
    <p>We’d love to hear from you. Fill in your details below:</p>

    <form class="contact-form" @submit.prevent="handleSubmit">
      <label>
        Name:
        <input v-model="name" type="text" required />
      </label>

      <label>
        Email:
        <input v-model="email" type="email" required />
      </label>

      <label>
        Message:
        <textarea v-model="message" rows="4" required></textarea>
      </label>

      <button type="submit">Send Message</button>
    </form>
  </section>
</template>

<script>
export default {
  name: "ContactPage",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  methods: {
    handleSubmit() {
      alert(`Thank you, ${this.name}! Your message has been received.`);
      this.name = this.email = this.message = "";
    },
  },
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

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  max-width: 400px;
  margin-top: 1.5rem;
}

input,
textarea {
  width: 100%;
  padding: 0.6rem;
  border: 1px solid var(--text-color);
  border-radius: 8px;
  background-color: var(--bg-color);
  color: var(--text-color);
  transition: border-color 0.2s ease;
}

input:focus,
textarea:focus {
  border-color: #888;
  outline: none;
}

button {
  padding: 0.7rem;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  background-color: var(--text-color);
  color: var(--bg-color);
  font-weight: bold;
  transition: background-color 0.3s ease, color 0.3s ease;
}

button:hover {
  background-color: var(--bg-color);
  color: var(--text-color);
  border: 1px solid var(--text-color);
}
</style>
