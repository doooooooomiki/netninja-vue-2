<template>
  <section>
    <h1>Categories</h1>
    <nav>
      <ul v-if="categories">
        <li v-for="category in categories" :key="category">
          <router-link :to="`/categories/${category}`">{{
            category
          }}</router-link>
        </li>
      </ul>
      <ul v-if="loading">
        <li>loading...</li>
      </ul>
    </nav>
    <router-view></router-view>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "CategoriesView",
  data() {
    return {
      loading: false,
      categories: null,
      error: null,
    };
  },
  created() {
    this.fetchCategories();
  },
  methods: {
    fetchCategories() {
      this.loading = true;
      fetch("https://fakestoreapi.com/products/categories")
        .then((res) => res.json())
        .then((categories) => {
          this.categories = categories;
          this.loading = false;
        });
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
