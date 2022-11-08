<template>
  <section v-if="isPublished">
    <h2>{{ title }}</h2>
    <p>Likes: {{ likes }}</p>
    <h3>One-Way Data Flow</h3>
    <p>
      All props form a one-way-down binding between the child property and the
      parent one: when the parent property updates, it will flow down to the
      child, but not the other way around. This prevents child components from
      accidentally mutating the parent’s state, which can make your app’s data
      flow harder to understand.
    </p>
    <p>
      In addition, every time the parent component is updated, all props in the
      child component will be refreshed with the latest value. This means you
      should not attempt to mutate a prop inside a child component. If you do,
      Vue will warn you in the console.
    </p>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "ComponentProps",
  props: {
    title: String,
    likes: Number,
    isPublished: Boolean,
  },
  mounted() {
    console.log(`property likes: ${this.$props.likes}`);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
