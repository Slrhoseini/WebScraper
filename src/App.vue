<template>
  <v-app id="inspire">
    <Header />
    <SubHeader />
    <Words />
    <Chart />
  </v-app>
</template>

<script>
import Header from "./components/Head-er.vue";
import SubHeader from "./components/Sub-Header.vue";
import Chart from './components/Bar-Chart.vue'
import Words from './components/Spec-Words.vue'

export default {
  name: "App",

  components: {
    Header,
    SubHeader,
    Chart,
    Words
  },

  data: () => ({
    //
  }),
};
</script>
