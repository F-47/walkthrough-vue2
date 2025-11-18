<template>
  <header>
    <router-link class="logo" to="/">F47</router-link>
    <nav>
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/products">Products</router-link></li>
      </ul>
    </nav>
    <button>Contact Us</button>
  </header>
</template>

<script>
export default {
  name: "HeaderComponent",
};
</script>

<style scoped>
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 2rem;
  background-color: #1a1a1a;
  color: #fff;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
}

nav ul {
  display: flex;
  list-style: none;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
}

nav ul li a {
  text-decoration: none;
  color: #fff;
  font-weight: 500;
  transition: color 0.3s;
}

nav ul li a:hover {
  color: #ff6f61;
}

button {
  padding: 0.5rem 1rem;
  background-color: #ff6f61;
  border: none;
  border-radius: 5px;
  color: #fff;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.2s;
}

button:hover {
  background-color: #ff856f;
  transform: translateY(-2px);
}

@media (max-width: 768px) {
  header {
    flex-direction: column;
    align-items: flex-start;
    gap: 1rem;
  }

  nav ul {
    flex-direction: column;
    gap: 0.5rem;
  }

  button {
    align-self: center;
  }
}
</style>
