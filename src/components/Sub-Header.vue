<template>
  <!-- <v-main class="text-center">
    <v-container align="center">
      <v-col cols="8" class="card rounded-xl rounded-t-0">
        <v-row align="center">
          <v-spacer></v-spacer>
          <v-col cols="6">

          <v-card
            :title="`Content ${n}`"
            :subtitle="`Subtitle for Content ${n}`"
            text="Lorem ipsum dolor sit amet consectetur, adipisicing elit.?"
          ></v-card>
        </v-col>
          <v-spacer></v-spacer>
          <v-col cols="4">
          <v-text-field
            class="tfield"
            label="کلمه کلیدی مورد نظر را وارد کنید"
            prepend-inner-icon="mdi-magnify"
          ></v-text-field>
        </v-col>
          <v-spacer></v-spacer>
        </v-row>
      </v-col>
    </v-container>
  </v-main> -->
  <v-main>
    <v-container align="center">
      <v-col class="card rounded-xl rounded-t-0" cols="8" align="center">
        <v-row class="ma-2">
          <v-spacer></v-spacer>
          <v-btn
            color="#36597D"
            class="addbtn"
            append-icon="mdi-plus"
            size="x-large"
          >
            اضافه کردن
          </v-btn>
          <v-spacer></v-spacer>
          <v-col cols="3" class="tfield">
            <v-text-field
              class="tfield2"
              variant="outlined"
              label="کلمه کلیدی مورد نظر را وارد کنید"
              prepend-inner-icon="mdi-magnify"
              :style="searchFieldStyle"
            >
            </v-text-field>
          </v-col>
          <v-spacer></v-spacer>
        </v-row>
      </v-col>
    </v-container>
  </v-main>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
* {
  font-family: Vazirmatn, sans-serif;
}
.addbtn {
  align-self: center;
  color: white !important;
}
.tfield {
  align-items: center;
  text-align: center;
  background-color: #fff;
  height: 80px;
  border-radius: 10px;
}

/* .tfield2 {
  align-items: center;
  text-align: center;
  background-color: #fff;
  height: 75px;
  padding: 10px;
  border-radius: 10px;
} */
.card {
  background-color: #2ebfa5;
}
</style>

<script>
export default {
  data: () => ({
    computed: {
      searchFieldStyle() {
        let style = {};
        if (this.$vuetify.breakpoint.smAndDown) {
          style.opacity = "1.0";
        } else if (this.$vuetify.breakpoint.mdAndDown) {
          style.width = "50%";
        }

        return style;
      },
    },
    menuItems: {
      type: Array,
      default: () => [
        {
          link: "#",
          name: "Dashboard",
          tooltip: "Dashboard",
          icon: "mdi-view-grid-outline",
        },
        {
          link: "#",
          name: "Chart",
          tooltip: "Chart",
          icon: "mdi-chart-line",
        },
      ],
    },
  }),
};
</script>
