<template>
  <button @click="increment()">You clicked me {{ count }} times</button>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IncrementButton",
  data: function () {
    return {
      count: 0,
    };
  },
  methods: {
    increment: function () {
      this.count++;
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
