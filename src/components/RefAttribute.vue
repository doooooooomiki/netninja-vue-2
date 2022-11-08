<template>
  <section>
    <h2 ref="h2">Ref Attribute</h2>
    <p ref="p">
      ref is used to register a reference to an element or a child component.
      The reference will be registered under the parent component’s $refs
      object. If used on a plain DOM element, the reference will be that
      element; if used on a child component, the reference will be component
      instance
    </p>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "RefAttribute",
  mounted() {
    console.log("mounted");
    console.log(this.$refs);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
