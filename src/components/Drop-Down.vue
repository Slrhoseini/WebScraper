<template>
  <div class="dots text-center">
    <v-menu>
      <template v-slot:activator="{ props }">
        <!-- <v-btn icon="mdi-menu" v-bind="props" class="elevation-2 mr-3"></v-btn> 
        class="elevation-2"
          color="#F1F5F9"
          variant="flat"
        -->
        <v-btn icon v-bind="props">
          <v-icon color="#36597D" size="30">mdi-menu</v-icon>
        </v-btn>
      </template>
      <v-list>
        <v-list-item class="popv" v-for="(item, i) in items" :key="i">
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: "نمای کلی" },
      { title: "تحلیل اطلاعات" },
      { title: "سازمان ها" },
      { title: "لیست اطلاعات" },
    ],
  }),
};
</script>

<style>
.dots {
  text-align: center;
}
.popv {
  font-size: 18px;
  transition: all 0.7s ease;
}
.popv:hover {
  cursor: pointer;
  transition: all 0.7s ease;
  transform: translateY(-15%);
  /* background-color: #DEDEDE;
  border-radius: 15px; 
  */
}
</style>
