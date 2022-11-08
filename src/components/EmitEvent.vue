<template>
  <section>
    <h2>Emit Event</h2>
    <button @click="emit">emit now</button>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "EmitEvent",
  data() {
    return {
      title: "Mr Mitten",
      emoji: "🐱",
    };
  },
  methods: {
    emit() {
      const catEmoji = {
        title: this.title,
        emoji: this.emoji,
      };
      this.$emit("my-event", catEmoji);
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
