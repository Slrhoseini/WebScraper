<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent width="500px">
      <template v-slot:activator="{ props }">
        <v-btn color="blue" v-bind="props" class="mb-4"> only a test for dialog </v-btn>
      </template>
      <!-- <v-card>
        <v-card-title class="text-h5">
          Use Google's location service?
        </v-card-title>
        <v-card-text
          >Let Google help apps determine location. This means sending anonymous
          location data to Google, even when no apps are running.</v-card-text
        >
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="green-darken-1" variant="text" @click="dialog = false">
            Disagree
          </v-btn>
          <v-btn color="green-darken-1" variant="text" @click="dialog = false">
            Agree
          </v-btn>
        </v-card-actions>
      </v-card> -->
      <v-card class="mx-auto" color="#36597D" width="500">
        <v-toolbar flat color="blue">
          <v-btn icon="mdi-account"></v-btn>

          <v-spacer></v-spacer>
          <v-toolbar-title class="font-weight-light">
            کلمات کلیدی
          </v-toolbar-title>
          <v-btn icon @click="isEditing = !isEditing">
            <v-fade-transition leave-absolute>
              <v-icon v-if="isEditing">mdi-close</v-icon>

              <v-icon v-else>mdi-pencil</v-icon>
            </v-fade-transition>
          </v-btn>
        </v-toolbar>

        <v-card-text>
          <div class="tfield2">
            <v-text-field
              class="tfield3 text-black"
              variant="outlined"
              label="کلمه کلیدی خود را وارد کنید"
              prepend-inner-icon="mdi-magnify"
              density="compact"
            >
            </v-text-field>
          </div>
          <!-- <v-autocomplete
            :disabled="!isEditing"
            :items="states"
            :custom-filter="customFilter"
            color="white"
            item-title="name"
            item-value="abbr"
            label="State"
            class="text-white"
          ></v-autocomplete> -->
          <v-select
            :items="carditems"
            :custom-filter="customFilter"
            item-title="name"
            item-value="abbr"
            label="کلمات کلیدی :"
            class="text-white pa-5"
            multiple
          ></v-select>
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn @click="dialog = false" color="white"> اعمال کردن </v-btn>
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

<style></style>
