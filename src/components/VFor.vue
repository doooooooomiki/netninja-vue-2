<template>
  <section>
    <h2>v-for</h2>
    <ul>
      <li v-for="tutor in tutors" :key="tutor.id">
        <span>{{ tutor.name }} is teaching {{ tutor.class }}</span>
      </li>
    </ul>
  </section>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "VFor",
  data() {
    return {
      tutors: [
        {
          id: 1,
          name: "Hohn",
          class: "Physics",
        },
        {
          id: 2,
          name: "Mill",
          class: "Mathmatics",
        },
      ],
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
