<template>
  <section>
    <h2>two way baby</h2>
    <input type="text" v-model="input" />
    <output>input: {{ input }}</output>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "TwoWayDataBinding",
  data: function () {
    return {
      input: "",
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
