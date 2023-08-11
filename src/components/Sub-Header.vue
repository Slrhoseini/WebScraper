<template>
  <v-main>
    <div class="foot">
      <v-row
        class="card rounded-xl rounded-t-0 elevation-8"
        align="center"
        no-gutters
      >
        <v-spacer></v-spacer>
        <v-dialog v-model="dialog" persistent width="800px">
          <template v-slot:activator="{ props }">
            <v-btn
              v-bind="props"
              color="#36597D"
              class="addbtn"
              append-icon="mdi-plus"
              size="x-large"
            >
              اضافه کردن
            </v-btn>
          </template>
          <v-row justify="center">
            <v-card class="mx-auto" width="800">
              <v-toolbar flat color="blue">
                <!-- <v-btn icon="mdi-file-search"></v-btn> -->
                <small class="pa-5">حداکثر ۵ مورد را میتوان انتخاب کرد *</small>
                <v-spacer></v-spacer>
                <p class="words1 pa-5">کلمات کلیدی</p>
              </v-toolbar>
              <v-card-text>
                <v-row align="center" no-gutters>
                  <v-spacer></v-spacer>
                  <v-btn
                    color="#36597D"
                    class="addbtn"
                    append-icon="mdi-plus"
                    size="large"
                  >
                    اضافه کردن
                  </v-btn>
                  <v-spacer></v-spacer>
                  <v-col>
                    <div class="tfield22">
                      <v-text-field
                        class="tfield33 text-black"
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
                <v-select
                  :items="carditems"
                  :custom-filter="customFilter"
                  item-title="name"
                  item-value="abbr"
                  label="کلمات کلیدی :"
                  class="pa-5"
                  multiple
                  variant="outlined"
                  chips
                  closable-chips
                ></v-select>
              </v-card-text>
              <v-divider></v-divider>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                  @click="dialog = false"
                  color="white"
                  class="addbtnn my-3 mx-5"
                  size="large"
                >
                  اعمال کردن
                </v-btn>

                <v-btn
                  @click="dialog = false"
                  color="white"
                  class="addbtnn my-3 mx-5"
                  size="large"
                >
                  بستن
                </v-btn>
                <v-spacer></v-spacer>
              </v-card-actions>

              <!-- <v-snackbar
          v-model="hasSaved"
          :timeout="2000"
          attach
          position="absolute"
          location="bottom left"
        >
          Your profile has been updated
        </v-snackbar> -->
            </v-card>
          </v-row>
        </v-dialog>
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

.words1 {
  font-size: 20px;
}
.tfield22 {
  background-color: #fff;
  border-radius: 10px;
  min-width: 300px;
}
.tfield33 {
  align-items: center;
  text-align: center;
  height: 65px;
  padding: 10px;
}
.addbtnn {
  align-self: center;
  background-color: #36597d !important;
}
</style>

<script>
export default {
  data: () => ({
    hasSaved: false,
    dialog: false,
    isEditing: null,
    selected: [],
    carditems: [
      "Username",
      "Role",
      "Email",
      "First Name",
      "Last Name",
      "Timezone",
      "Expiration Time",
      "Created By",
      "Creation Time",
      "Last Modified",
      "Last Modification Time",
    ],
    states: [
      { name: "Florida", abbr: "FL", id: 1 },
      { name: "Georgia", abbr: "GA", id: 2 },
      { name: "Nebraska", abbr: "NE", id: 3 },
      { name: "California", abbr: "CA", id: 4 },
      { name: "New York", abbr: "NY", id: 5 },
    ],
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
