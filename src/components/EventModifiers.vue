<template>
  <section>
    <h2>{{ title }}</h2>

    <div @click="onNothing">
      <!-- the click event's propagation will be stopped -->
      <a href="#" v-on:click.stop="onClickStop">propagation will be stopped</a>
    </div>

    <!-- the submit event will no longer reload the page -->
    <form v-on:submit.prevent="onSubmitPrevent">
      <button type="submit">Submit</button>
    </form>

    <!-- https://v2.vuejs.org/v2/guide/events.html#Key-Modifiers -->
    <input v-on:keyup.enter="onEnter" />
  </section>
</template>

<script lang="ts">
// Event Modifiers
// https://v2.vuejs.org/v2/guide/events.html#Event-Modifiers
// It is a very common need to call event.preventDefault() or event.stopPropagation()
// inside event handlers. Although we can do this easily inside methods,
// it would be better if the methods can be purely about data logic rather
// than having to deal with DOM event details.

import Vue from "vue";

export default Vue.extend({
  name: "EventModifiers",
  data: function () {
    return {
      title: "Event Modifiers",
    };
  },
  methods: {
    onClickStop: function () {
      console.log("stop propagation");
    },
    onNothing: function () {
      console.log("nothing");
    },
    onSubmitPrevent: function () {
      console.log("prevent default");
    },
    onEnter: function (event: KeyboardEvent) {
      console.log(event.key);
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
