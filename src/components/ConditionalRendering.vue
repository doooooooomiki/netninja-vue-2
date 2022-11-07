<template>
  <section>
    <h2>Conditional Rendering</h2>

    <p>
      Vue tries to render elements as efficiently as possible, often re-using
      them instead of rendering from scratch. Beyond helping make Vue very fast,
      this can have some useful advantages. For example, if you allow users to
      toggle between multiple login types:
    </p>

    <template v-if="loginType === 'username'">
      <label>Username</label>
      <input placeholder="Enter your username" />
    </template>

    <template v-else>
      <label>Email</label>
      <input placeholder="Enter your email address" />
    </template>

    <p>
      This isn’t always desirable though, so Vue offers a way for you to say,
      “These two elements are completely separate - don’t re-use them.” Add a
      key attribute with unique values:
    </p>

    <template v-if="loginType === 'username'">
      <label>Username</label>
      <input placeholder="Enter your username" key="username-input" />
    </template>

    <template v-else>
      <label>Email</label>
      <input placeholder="Enter your email address" key="email-input" />
    </template>

    <br /><button @click="toggleLoginType">toggle login type</button><br />

    <p v-show="ook">v-show</p>
    <p>v-show only toggles the display CSS property of the element.</p>
  </section>
</template>

<script lang="ts">
// https://v2.vuejs.org/v2/guide/conditional.html
import Vue from "vue";

export default Vue.extend({
  name: "ConditionalRendering",
  data: function () {
    return {
      loginType: "username",
      ook: true,
    };
  },
  methods: {
    toggleLoginType: function () {
      this.loginType = this.loginType === "username" ? "email" : "username";
    },
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
