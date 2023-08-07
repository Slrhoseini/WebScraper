<template>
  <v-main>
    <div class="foot">
      <v-row
        class="card rounded-xl rounded-t-0 elevation-8"
        align="center"
        no-gutters
      >
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
        <v-col>
          <div class="tfield2">
            <v-text-field
              class="tfield3 text-black"
              variant="outlined"
              label="کلمه کلیدی مورد نظر را وارد کنید"
              prepend-inner-icon="mdi-magnify"
              density="compact"
            >
            </v-text-field>
          </div>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </div>
    <v-container align="center">
      <v-col
        class="blocks rounded-xl rounded-t-0"
        cols="10"
        md="12"
        sm="10"
        align="center"
      >
        <v-row>
          <v-col>
            <v-btn
              color="#36597D"
              class="addbtn2 rounded-bs-xl rounded-te-xl"
              append-icon="mdi-file-document-outline"
              size="x-large"
            >
              مجموع اطلاعات
              <br />
              +۸۵۰,۰۰۰
            </v-btn>
          </v-col>
          <v-col>
            <v-btn
              color="#36597D"
              class="addbtn2 rounded-bs-xl rounded-te-xl"
              append-icon="mdi-file-document-outline"
              size="x-large"
            >
              مجموع اطلاعات
              <br />
              +۸۵۰,۰۰۰
            </v-btn>
          </v-col>
          <v-col>
            <v-btn
              color="#36597D"
              class="addbtn2 rounded-bs-xl rounded-te-xl"
              append-icon="mdi-file-document-outline"
              size="x-large"
            >
              مجموع سازمان ها
              <br />
              +۸۵۰,۰۰۰
            </v-btn>
          </v-col>
          <v-col>
            <v-btn
              class="addbtn2 rounded-bs-xl rounded-te-xl"
              color="#36597D"
              append-icon="mdi-file-document-outline"
              size="x-large"
            >
              مجموع اطلاعات
              <br />
              +۸۵۰,۰۰۰
            </v-btn>
          </v-col>
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
.addbtn2 {
  align-self: center;
  color: white !important;
}
.tfield {
  align-items: center;
  text-align: center;
  background-color: #fff;
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
.tfield2 {
  background-color: #fff;
  border-radius: 10px;
  min-width: 200px;
}
.tfield3 {
  align-items: center;
  text-align: center;
  height: 65px;
  padding: 10px;
}
.card {
  background-color: #2ebfa5;
  height: 70px;
}
.foot {
  position: fixed;
  width: 100%;
  z-index: 100;
}
.blocks {
  /* background-color: red; */
  margin-top: 60px;
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
