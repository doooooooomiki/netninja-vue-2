<template>
  <section>
    <h1>Post View</h1>
    <p>user: {{ $route.params.username }}</p>
    <p>post id: {{ $route.params.post_id }}</p>
    <p>route params:</p>
    <pre>{{ $route.params }}</pre>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Reiciendis unde
      illo culpa, natus dignissimos impedit facere error necessitatibus autem
      iure, ullam aliquam iste expedita earum sed accusantium obcaecati ipsum
      nihil.
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla quasi
      laborum dolor autem recusandae harum. Harum commodi eligendi tempore
      voluptatibus in laudantium, cumque quidem reprehenderit voluptas illo quam
      velit fuga.
    </p>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "PostView",
  mounted() {
    console.log(this.$route.params);
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
