<template>
  <v-app id="inspire">
    <Header />
    <SubHeader />
  </v-app>
</template>

<script>
import Header from "./components/Head-er.vue";
import SubHeader from "./components/Sub-Header.vue";

export default {
  name: "App",

  components: {
    Header,
    SubHeader
  },

  data: () => ({
    //
    drawer: false,
  }),
};
</script>
