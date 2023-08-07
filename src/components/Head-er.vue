<template>
  <v-app-bar color="#ECF5FE" class="elevation-2">
    <v-btn icon class="icons ml-8 elevation-3" color="#F1F5F9" variant="flat">
      <v-icon color="#36597D" size="25">mdi-logout</v-icon>
    </v-btn>
    <v-btn icon class="icons elevation-3" color="#F1F5F9" variant="flat">
      <v-icon color="#36597D" size="25">mdi-account-box-outline</v-icon>
    </v-btn>
    <input class="in2" type="checkbox" id="darkmode-toggle" />
    <label class="lab2" for="darkmode-toggle">
      <svg
        class="moon"
        width="35px"
        height="35px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M3.32031 11.6835C3.32031 16.6541 7.34975 20.6835 12.3203 20.6835C16.1075 20.6835 19.3483 18.3443 20.6768 15.032C19.6402 15.4486 18.5059 15.6834 17.3203 15.6834C12.3497 15.6834 8.32031 11.654 8.32031 6.68342C8.32031 5.50338 8.55165 4.36259 8.96453 3.32996C5.65605 4.66028 3.32031 7.89912 3.32031 11.6835Z"
          stroke="#000000"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
      <svg
        class="sun"
        width="35px"
        height="35px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M12 3V4M12 20V21M4 12H3M6.31412 6.31412L5.5 5.5M17.6859 6.31412L18.5 5.5M6.31412 17.69L5.5 18.5001M17.6859 17.69L18.5 18.5001M21 12H20M16 12C16 14.2091 14.2091 16 12 16C9.79086 16 8 14.2091 8 12C8 9.79086 9.79086 8 12 8C14.2091 8 16 9.79086 16 12Z"
          stroke="#000000"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </label>
    <v-spacer></v-spacer>
    <div class="tabs hidden-sm hidden-xs">
      <button v-for="link in links" :key="link" class="tabs2 mx-7">
        {{ link }}
      </button>
    </div>
    <!-- <v-btn class="tabs" to="/">نمای کلی</v-btn>
    <v-btn class="tabs" to="/">تحلیل اطلاعات</v-btn>
    <v-btn class="tabs" to="/">سازمان ها</v-btn>
    <v-btn class="tabs" to="/">لیست اطلاعات</v-btn> -->
    <v-avatar size="50" class="ml-2">
      <v-img src="../../src/assets/lgo.png"></v-img>
    </v-avatar>
  </v-app-bar>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
* {
  font-family: Vazirmatn, sans-serif;
}
.icons {
  margin: 0rem 0 0 1.5rem;
}
.tabs {
  margin-top: auto;
}
.tabs2 {
  font-family: Vazirmatn, sans-serif;
  font-size: 18px;
  font-weight: bold;
  position: relative;
  text-decoration: none;
  padding-bottom: 20px;
}
.tabs2::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 4px;
  border-radius: 4px;
  background-color: #36597d;
  bottom: 0;
  left: 0;
  transform-origin: right;
  transform: scaleX(0);
  transition: transform 0.3s ease-in-out;
}
.tabs2:hover::before {
  transform-origin: left;
  transform: scaleX(1);
}

.lab2 {
  margin: 0rem 0 0 1.5rem;
  width: 90px;
  height: 45px;
  position: relative;
  display: block;
  background: #ebebeb;
  border-radius: 200px;
  box-shadow: inset 0px 5px 15px rgba(0, 0, 0, 0.4),
    inset 0px -5px 15px rgba(255, 255, 255, 0.4);
  cursor: pointer;
  transition: 0.3s;
}
.lab2:after {
  content: "";
  width: 35px;
  height: 35px;
  top: 5px;
  left: 5px;
  position: absolute;
  background: linear-gradient(180deg, #ffcc89, #d8860b);
  border-radius: 50px;
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.2);
  transition: 0.3s;
}
.in2 {
  width: 0;
  height: 0;
  visibility: hidden;
}
.in2:checked + .lab2 {
  background: #242424;
}
.in2:checked + .lab2:after {
  left: 15px;
  transform: translateX(100%);
  background: linear-gradient(180deg, #777, #313131);
}
/* label:active:after {
  width: 50px;
} */
.lab2 svg {
  position: absolute;
  top: 5px;
  z-index: 100;
}
.lab2 svg.sun {
  left: 5px;
  fill: #fff;
  transition: 0.3s;
}
.lab2 svg.moon {
  left: 50px;
  fill: #7e7e7e;
  transition: 0.3s;
}
.in2:checked + .lab2 svg.sun {
  fill: #7e7e7e;
}
.in2:checked + .lab2 svg.moon {
  fill: #fff;
}
@media (max-width: 770px) {

}
</style>

<script>
export default {
  data: () => ({
    links: ["لیست اطلاعات", "سازمان ها", "تحلیل اطلاعات", "نمای کلی"],
    // links: ["L1", "link 2"],
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
