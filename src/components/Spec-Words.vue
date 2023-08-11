<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent width="800px">
      <template v-slot:activator="{ props }">
        <v-btn color="blue" v-bind="props" class="mb-4">
          only a test for dialog
        </v-btn>
      </template>
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
    </v-dialog>
  </v-row>
</template>

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
  }),

  methods: {
    customFilter(itemTitle, queryText, item) {
      const textOne = item.raw.name.toLowerCase();
      const textTwo = item.raw.abbr.toLowerCase();
      const searchText = queryText.toLowerCase();

      return (
        textOne.indexOf(searchText) > -1 || textTwo.indexOf(searchText) > -1
      );
    },
    save() {
      this.isEditing = !this.isEditing;
      this.hasSaved = true;
    },
  },
};
</script>

<style>
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
