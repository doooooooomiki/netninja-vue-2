<template>
  <section>
    <h1>User View</h1>
    <p>user: {{ $route.params.username }}</p>
    <nav>
      <ul>
        <li>
          <router-link :to="`/user/${$route.params.username}/profile`"
            >profile</router-link
          >
        </li>
        <li>
          <router-link :to="`/user/${$route.params.username}/posts`"
            >posts</router-link
          >
        </li>
      </ul>
    </nav>
    <router-view></router-view>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "UserView",
  mounted() {
    console.log(this.$route.params);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
