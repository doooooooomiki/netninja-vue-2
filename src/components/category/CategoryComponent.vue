<template>
  <section>
    <h2>Products</h2>
    <ul v-if="loading">
      <li>loading...</li>
    </ul>
    <ul v-if="products">
      <li v-for="product in products" :key="product.id">
        <span>{{ product.title }}</span>
      </li>
    </ul>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "CategoryComponent",
  data() {
    return {
      loading: false,
      products: null,
      error: null,
    };
  },
  mounted() {
    console.log(this.$route.params);
  },
  created() {
    this.fetchCategories();
  },
  watch: {
    // call again the method if the route changes
    $route: function () {
      this.products = null;
      this.fetchCategories();
    },
  },
  methods: {
    fetchCategories() {
      this.loading = true;
      fetch(
        `https://fakestoreapi.com/products/category/${this.$route.params.category}`
      )
        .then((res) => res.json())
        .then((categories) => {
          this.products = categories;
          this.loading = false;
        });
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
