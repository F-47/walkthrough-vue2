<template>
  <div class="products-container">
    <!-- Search input -->
    <div class="header">
      <h1>All Products</h1>
      <input type="search" v-model="search" placeholder="Search products..." />
    </div>
    <div v-if="loading">Loading...</div>
    <div v-else>
      <div class="cards-container">
        <!-- Loop through filtered products -->
        <div class="card" v-for="product in filteredProducts" :key="product.id">
          <h3>{{ product.title }}</h3>
          <p>Price: ${{ product.price }}</p>
        </div>
        <div v-if="filteredProducts.length === 0">No products found.</div>
      </div>
    </div>
    <button @click="num += 2">{{ num }}</button>
  </div>
</template>

<script>
export default {
  name: "Products",
  data() {
    return {
      search: "",
      num: 0,
      loading: false,
      products: [
        { id: 1, title: "Laptop", price: 1200 },
        { id: 2, title: "Phone", price: 800 },
        { id: 3, title: "Headphones", price: 150 },
      ],
    };
  },
  computed: {
    filteredProducts() {
      const searchTerm = this.search.toLowerCase();
      return this.products.filter((product) =>
        product.title.toLowerCase().includes(searchTerm)
      );
    },
  },
  methods: {
    delayedUpdate() {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
      }, 5000);
    },
  },
  mounted() {
    this.delayedUpdate();
  },
};
</script>

<style scoped>
.products-container {
  margin-top: 20px;
  padding: 1rem 2rem;
}
.products-container .header {
  display: flex;
  justify-content: space-between;
}
.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 20px;
}
.card {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
  transition: box-shadow 0.3s ease, border-color 0.3s ease;
}
.card:hover {
  box-shadow: 4px 4px 16px rgba(0, 0, 0, 0.2);
  border-color: #888;
}
input[type="search"] {
  padding-block: 10px;
  padding-inline: 20px;
  border-radius: 5px;
  border: 1px solid #b9b9b9;
}
</style>
