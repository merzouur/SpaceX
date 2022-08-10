<template>
  <MainTitle title="Space X" />
  <Section title="Next launches" content="NextLaunch" />
  

</template>

<script>
import MainTitle from "./components/MainTitle.vue";
import Section from "./components/Section.vue";


export default {
  name: "App",
  components: {
    MainTitle: MainTitle,
    Section: Section,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
