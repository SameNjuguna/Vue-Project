<template>
  <section class="services-page">
    <h2>Services Page</h2>
    <p>Below is a list of tasks fetched from an API.</p>

    <!-- 🔍 Search Bar -->
    <input
      v-model="searchQuery"
      type="text"
      placeholder="Search todos..."
      class="search-bar"
    />

    <!-- 🗂️ Todos Grid -->
    <div class="cards-container">
      <div
        v-for="todo in filteredTodos"
        :key="todo.id"
        class="card"
      >
        <h3>{{ todo.title }}</h3>
        <p>Status:
          <strong :class="todo.completed ? 'done' : 'pending'">
            {{ todo.completed ? 'Completed' : 'Pending' }}
          </strong>
        </p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ServicesPage",
  data() {
    return {
      todos: [],
      searchQuery: "",
    };
  },
  computed: {
    filteredTodos() {
      return this.todos.filter(todo =>
        todo.title.toLowerCase().includes(this.searchQuery.toLowerCase())
      );
    },
  },
  mounted() {
    this.fetchTodos();
  },
  methods: {
    async fetchTodos() {
      try {
        const res = await fetch("https://jsonplaceholder.typicode.com/users/1/todos");
        this.todos = await res.json();
      } catch (error) {
        console.error("Error fetching todos:", error);
      }
    },
  },
};
</script>

<style>
.services-page {
  padding: 2rem;
  background-color: var(--bg-color);
  color: var(--text-color);
  min-height: 100vh;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.search-bar {
  display: block;
  margin: 1rem 0 2rem;
  padding: 0.6rem 1rem;
  font-size: 1rem;
  width: 100%;
  max-width: 400px;
  background-color: var(--bg-color);
  color: var(--text-color);
  border: 1px solid var(--text-color);
  border-radius: 8px;
  outline: none;
  transition: all 0.2s ease;
}

.search-bar::placeholder {
  color: var(--text-color);
  opacity: 0.6;
}

.search-bar:focus {
  border-color: #888;
}

.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
}

.card {
  background: var(--bg-color);
  color: var(--text-color);
  border: 1px solid var(--text-color);
  border-radius: 12px;
  padding: 1rem;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease, background-color 0.3s ease;
}

.card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.done {
  color: limegreen;
}

.pending {
  color: tomato;
}
</style>
