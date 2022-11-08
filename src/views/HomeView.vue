<template>
  <div class="home">
    <HelloWorld msg="Welcome to Home" />
    <ul>
      <li>
        <a target="_blank" :href="urlVBind">v-bind</a>
      </li>
      <li>
        <a v-html="aVHtml"></a>
      </li>
    </ul>
    <IncrementButton />
    <EventModifiers />
    <TwoWayDataBinding />
    <ComputedProperties />
    <ConditionalRendering />
    <VFor />
    <RefAttribute />
    <!-- Even though `42` is static, we need v-bind to tell Vue that -->
    <!-- this is a JavaScript expression rather than a string.       -->
    <ComponentProps isPublished title="Props" :likes="42" />
    <EmitEvent @my-event="myEventFired" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import HelloWorld from "@/components/HelloWorld.vue"; // @ is an alias to /src
import IncrementButton from "@/components/IncrementButton.vue";
import EventModifiers from "@/components/EventModifiers.vue";
import TwoWayDataBinding from "@/components/TwoWayDataBinding.vue";
import ComputedProperties from "@/components/ComputedProperties.vue";
import ConditionalRendering from "@/components/ConditionalRendering.vue";
import VFor from "@/components/VFor.vue";
import RefAttribute from "@/components/RefAttribute.vue";
import ComponentProps from "@/components/ComponentProps.vue";
import EmitEvent from "@/components/EmitEvent.vue";

export default Vue.extend({
  name: "HomeView",
  data: function () {
    return {
      urlVBind: "https://v2.vuejs.org/v2/api/#v-bind",
      urlVHtml: "https://v2.vuejs.org/v2/api/#v-html",
      aVHtml:
        "<a target='_blank' href='https://v2.vuejs.org/v2/api/#v-html'>v-html</a>",
    };
  },
  components: {
    HelloWorld,
    IncrementButton,
    EventModifiers,
    TwoWayDataBinding,
    ComputedProperties,
    ConditionalRendering,
    VFor,
    RefAttribute,
    ComponentProps,
    EmitEvent,
  },
  methods: {
    myEventFired(e: any) {
      console.log(e);
    },
  },
});
</script>
