<template>
  <v-app id="inspire">
    <Header />
    <SubHeader />
    <Chart />
  </v-app>
</template>

<script>
import Header from "../components/Head-er.vue";
import SubHeader from "../components/Sub-Header.vue";
import Chart from "../components/Bar-Chart.vue";

export default {
  name: "App",

  components: {
    Header,
    SubHeader,
    Chart,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
* {
  font-family: Vazirmatn, sans-serif;
}
</style>