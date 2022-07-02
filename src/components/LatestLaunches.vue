<template>
  <div class="lastest-launches"></div>
</template>

<script>
export default {
  name: "LastestLaunches",
  data() {
    return {
      launches: [],
    };
  },
  methods: {
    getLatestLaunches() {
      fetch("https://api.spacexdata.com/v4/launches/query", {
        method: "POST",
        body: JSON.stringify({
          query: {
            success: true,
          },
          options: {
            limit: 1,
            sort: {
              flight_number: "desc",
            },
          },
        }),
      })
        .then((response) => response.json())
        .then((data) => {
          //console.log(data);
        });
    },
  },
  mounted() {
    this.getLatestLaunches();
  },
};
</script>

<style scoped>
h1 {
  margin: 40px 0 0;
}
</style>
