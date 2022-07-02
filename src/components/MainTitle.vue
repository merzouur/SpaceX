<template>
  <div class="main-title">
    <h1>{{ title }}</h1>
  </div>
</template>

<script>
export default {
  name: "MainTitle",
  props: {
    title: String,
  },
};
</script>

<style scoped>
h1 {
  margin: 40px 0 0;
}
</style>
