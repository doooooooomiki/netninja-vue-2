<template>
  <div class="home">
    <IncrementButton />
    <HelloWorld msg="Welcome to Home" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import IncrementButton from "@/components/IncrementButton.vue"; // @ is an alias to /src

export default Vue.extend({
  name: "HomeView",
  components: {
    HelloWorld,
    IncrementButton,
  },
});
</script>
