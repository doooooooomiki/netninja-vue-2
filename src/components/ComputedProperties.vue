<template>
  <section>
    <h2>Computed Properties</h2>
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <p>
      A computed property will only re-evaluate when some of its reactive
      dependencies have changed. This means as long as message has not changed,
      multiple access to the reversedMessage computed property will immediately
      return the previously computed result without having to run the function
      again.
    </p>
  </section>
</template>

<script lang="ts">
// https://v2.vuejs.org/v2/guide/computed.html#Computed-Properties
import Vue from "vue";

export default Vue.extend({
  name: "ComputedProperties",
  data: function () {
    return {
      message: "hello",
    };
  },
  computed: {
    reversedMessage: function () {
      return this.message.split("").reverse().join("");
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
