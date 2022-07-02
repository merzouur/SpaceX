<template>
  <div class="next-launch">
    <p>{{ name }}</p>
    <p>{{ launchDate.toLocaleString() }}</p>
    <p>{{ secondsLeftBeforeLaunch }}</p>
  </div>
</template>

<script>
export default {
  name: "NextLaunch",
  data() {
    return {
      name: String,
      launchDate: Date,
      secondsLeftBeforeLaunch: Number,
    };
  },
  methods: {
    async getNextLaunch() {
      const response = await fetch(
        "https://api.spacexdata.com/v4/launches/next"
      );

      const jsonResponse = await response.json();

      const { name, date_utc } = jsonResponse;

      this.name = name;
      this.launchDate = new Date(date_utc);
      this.secondsLeftBeforeLaunch = 0;
      this.computeSecondsBeforeLaunch();

      /*fetch("https://api.spacexdata.com/v4/launches/next")
        .then((response) => response.json())
        .then((data) => {
          const { name, date_utc } = data;

          this.name = name;
          this.launchDate = new Date(date_utc);
          this.secondsLeftBeforeLaunch = 0;
          this.computeSecondsBeforeLaunch();
        });*/
    },
    computeSecondsBeforeLaunch() {
      setInterval(() => {
        this.secondsLeftBeforeLaunch = Math.round(
          (this.launchDate - new Date()) / 1000
        );
      }, 1000);
    },
  },
  mounted() {
    this.getNextLaunch();
  },
};
</script>

<style scoped>
</style>