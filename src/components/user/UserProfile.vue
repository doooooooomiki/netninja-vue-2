<template>
  <section>
    <h2>Profile: {{ $route.params.username }}</h2>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "UserProfile",
  mounted() {
    console.log(this.$route.params);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
