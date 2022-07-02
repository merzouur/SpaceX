<template>
  <div class="section">
    <h2>{{ title }}</h2>
    <component :is="content"></component>
  </div>
</template>

<script>
import NextLaunch from "./NextLaunch.vue";
import LatestLaunches from "./LatestLaunches.vue";

export default {
  name: "Section",
  components: {
    NextLaunch,
    LatestLaunches,
  },
  props: {
    title: String,
    content: String,
  },
};
</script>