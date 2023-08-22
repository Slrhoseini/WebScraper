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
          <router-link :to="item.path">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </router-link>
        </v-list-item>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      { title: "نمای کلی", path: "/homee" },
      { title: "تحلیل اطلاعات", path: "/" },
      { title: "سازمان ها", path: "/tahlil" },
      { title: "لیست اطلاعات", path: "/" },
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
/* استایل خط کشیده شده (نشانگر باز شده قبلی) */
.popv:after {
  content: "";
  display: block;
  width: 100%;
  height: 2px;
  background-color: black;
}
/* استایل خط معمولی */
.v-list-item-title {
  color: black; /* رنگ متن خط‌های معمولی */
}

/* استایل خط کشیده شده (نشانگر باز شده قبلی) در حالت هاور */
.v-list-item:hover .popv:after {
  background-color: black;
}
</style>
