<template>
  <v-main>
    <div class="foot">
      <v-row
        class="card rounded-xl rounded-t-0 elevation-8"
        align="center"
        no-gutters
      >
        <!-- <v-dialog v-model="dialog" persistent width="800px">
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
            </v-card>
          </v-row>
        </v-dialog> -->
        <v-col>
          <v-dialog v-model="dialog2" persistent width="800px">
            <template v-slot:activator="{ props }">
              <div class="tfield2" v-bind="props">
                <v-text-field
                  class="tfield3 text-black"
                  variant="outlined"
                  label="کلمه کلیدی مورد نظر را وارد کنید"
                  prepend-inner-icon="mdi-magnify"
                  density="compact"
                  disabled
                >
                </v-text-field>
              </div>
            </template>
            <v-row justify="center">
              <v-card class="mx-auto" width="800">
                <v-toolbar flat color="blue">
                  <!-- <v-btn icon="mdi-file-search"></v-btn> -->
                  <small class="pa-5"
                    >حداکثر ۵ مورد را میتوان انتخاب کرد *</small
                  >
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
                  <!-- <v-select
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
                  ></v-select> -->
                  <div class="multiselect1">
                    <VueMultiselect
                      v-model="selected"
                      :options="options"
                      :multiple="true"
                      :close-on-select="false"
                      placeholder="Select option"
                      openDirection="bottom"
                      class="multiselect2"
                    >
                    </VueMultiselect>
                  </div>
                </v-card-text>
                <v-divider></v-divider>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                    @click="dialog2 = false"
                    color="white"
                    class="addbtnn my-3 mx-5"
                    size="large"
                  >
                    اعمال کردن
                  </v-btn>
                  <v-btn
                    @click="dialog2 = false"
                    color="white"
                    class="addbtnn my-3 mx-5"
                    size="large"
                  >
                    بستن
                  </v-btn>
                  <v-spacer></v-spacer>
                </v-card-actions>
              </v-card>
            </v-row>
          </v-dialog>
        </v-col>
      </v-row>
    </div>
  </v-main>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
.multiselect1 {
  margin-top: 20px;
  padding-bottom: 50px;
  margin-left: auto;
}
.multiselect2 {
  width: 96%;
  position: fixed;
}
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
    min-width: 200px;
} */
.tfield2 {
  background-color: #fff;
  border-radius: 10px;
  cursor: pointer;
  max-width: 285px;
  margin-left: auto;
  margin-right: auto;
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
  margin-top: 0;
}
.foot {
  position: fixed;
  width: 100%;
  z-index: 100;
}
.blocks {
  /* background-color: yellow; */
  margin-top: 60px;
}
.words1 {
  font-size: 20px;
}
.tfield22 {
  background-color: #fff;
  border-radius: 10px;
  min-width: 290px;
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
import VueMultiselect from "vue-multiselect";

export default {
  components: { VueMultiselect },
  data: () => ({
    hasSaved: false,
    dialog: false,
    dialog2: false,
    isEditing: null,
    selected: null,
    options: [
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
