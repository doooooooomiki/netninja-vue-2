<template>
  <button @click="increment">You clicked me {{ count }} times</button>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IncrementButton",

  // data
  // https://v2.vuejs.org/v2/api/#Options-Data
  // When defining a component, data must be declared as a function that returns
  // the initial data object, because there will be many instances created using the same definition
  data: function () {
    return {
      count: 0,
    };
  },

  // methods
  // https://v2.vuejs.org/v2/api/#methods
  // Note that you should _not_ use an arrow function to define a method
  // The reason is arrow functions bind the parent context,
  // so this will not be the Vue instance as you expect
  methods: {
    //  When listening to native DOM events, the method receives the native event
    // as the only argument. If using inline statement, the statement has access
    // to the special $event property: v-on:click="handle('ok', $event)".
    increment: function (event: MouseEvent) {
      this.count++;
      console.log(`event type: ${event.type} fired ${this.count} times`);
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
