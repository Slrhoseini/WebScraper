<template>
  <v-app-bar color="#ECF5FE" class="elevation-2">
    <v-btn icon class="icons ml-8 elevation-2" color="#F1F5F9" variant="flat">
      <v-icon color="#36597D" size="25">mdi-logout</v-icon>
    </v-btn>
    <v-btn icon class="icons elevation-2" color="#F1F5F9" variant="flat">
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
        <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
        <g
          id="SVGRepo_tracerCarrier"
          stroke-linecap="round"
          stroke-linejoin="round"
        ></g>
        <g id="SVGRepo_iconCarrier">
          <path
            d="M21.0672 11.8568L20.4253 11.469L21.0672 11.8568ZM12.1432 2.93276L11.7553 2.29085V2.29085L12.1432 2.93276ZM7.37554 20.013C7.017 19.8056 6.5582 19.9281 6.3508 20.2866C6.14339 20.6452 6.26591 21.104 6.62446 21.3114L7.37554 20.013ZM2.68862 17.3755C2.89602 17.7341 3.35482 17.8566 3.71337 17.6492C4.07191 17.4418 4.19443 16.983 3.98703 16.6245L2.68862 17.3755ZM21.25 12C21.25 17.1086 17.1086 21.25 12 21.25V22.75C17.9371 22.75 22.75 17.9371 22.75 12H21.25ZM2.75 12C2.75 6.89137 6.89137 2.75 12 2.75V1.25C6.06294 1.25 1.25 6.06294 1.25 12H2.75ZM15.5 14.25C12.3244 14.25 9.75 11.6756 9.75 8.5H8.25C8.25 12.5041 11.4959 15.75 15.5 15.75V14.25ZM20.4253 11.469C19.4172 13.1373 17.5882 14.25 15.5 14.25V15.75C18.1349 15.75 20.4407 14.3439 21.7092 12.2447L20.4253 11.469ZM9.75 8.5C9.75 6.41182 10.8627 4.5828 12.531 3.57467L11.7553 2.29085C9.65609 3.5593 8.25 5.86509 8.25 8.5H9.75ZM12 2.75C11.9115 2.75 11.8077 2.71008 11.7324 2.63168C11.6686 2.56527 11.6538 2.50244 11.6503 2.47703C11.6461 2.44587 11.6482 2.35557 11.7553 2.29085L12.531 3.57467C13.0342 3.27065 13.196 2.71398 13.1368 2.27627C13.0754 1.82126 12.7166 1.25 12 1.25V2.75ZM21.7092 12.2447C21.6444 12.3518 21.5541 12.3539 21.523 12.3497C21.4976 12.3462 21.4347 12.3314 21.3683 12.2676C21.2899 12.1923 21.25 12.0885 21.25 12H22.75C22.75 11.2834 22.1787 10.9246 21.7237 10.8632C21.286 10.804 20.7293 10.9658 20.4253 11.469L21.7092 12.2447ZM12 21.25C10.3139 21.25 8.73533 20.7996 7.37554 20.013L6.62446 21.3114C8.2064 22.2265 10.0432 22.75 12 22.75V21.25ZM3.98703 16.6245C3.20043 15.2647 2.75 13.6861 2.75 12H1.25C1.25 13.9568 1.77351 15.7936 2.68862 17.3755L3.98703 16.6245Z"
          ></path>
        </g>
      </svg>
      <svg
        class="sun"
        width="35px"
        height="35px"
        viewBox="0 0 24 24"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <g id="SVGRepo_bgCarrier" stroke-width="0"></g>
        <g
          id="SVGRepo_tracerCarrier"
          stroke-linecap="round"
          stroke-linejoin="round"
        ></g>
        <g id="SVGRepo_iconCarrier">
          <path
            d="M12 17.75C10.8628 17.75 9.75106 17.4128 8.80547 16.781C7.85989 16.1491 7.1229 15.2511 6.6877 14.2004C6.25249 13.1498 6.13862 11.9936 6.36049 10.8782C6.58235 9.76284 7.12999 8.73829 7.93414 7.93414C8.73829 7.12999 9.76284 6.58235 10.8782 6.36049C11.9936 6.13862 13.1498 6.25249 14.2004 6.6877C15.2511 7.1229 16.1491 7.85989 16.781 8.80547C17.4128 9.75106 17.75 10.8628 17.75 12C17.7474 13.5242 17.1407 14.9852 16.0629 16.0629C14.9852 17.1407 13.5242 17.7474 12 17.75ZM12 7.75C11.1594 7.75 10.3377 7.99926 9.63883 8.46626C8.93992 8.93325 8.39519 9.59701 8.07351 10.3736C7.75184 11.1502 7.66768 12.0047 7.83167 12.8291C7.99565 13.6536 8.40043 14.4108 8.9948 15.0052C9.58917 15.5996 10.3464 16.0044 11.1709 16.1683C11.9953 16.3323 12.8498 16.2482 13.6264 15.9265C14.403 15.6048 15.0668 15.0601 15.5337 14.3612C16.0007 13.6623 16.25 12.8406 16.25 12C16.2474 10.8736 15.7987 9.79417 15.0023 8.99772C14.2058 8.20126 13.1264 7.75264 12 7.75Z"
          ></path>
          <path
            d="M12 5C11.8019 4.99741 11.6126 4.91756 11.4725 4.77747C11.3324 4.63737 11.2526 4.44811 11.25 4.25V2.75C11.25 2.55109 11.329 2.36032 11.4697 2.21967C11.6103 2.07902 11.8011 2 12 2C12.1989 2 12.3897 2.07902 12.5303 2.21967C12.671 2.36032 12.75 2.55109 12.75 2.75V4.25C12.7474 4.44811 12.6676 4.63737 12.5275 4.77747C12.3874 4.91756 12.1981 4.99741 12 5Z"
          ></path>
          <path
            d="M12 22C11.8019 21.9974 11.6126 21.9176 11.4725 21.7775C11.3324 21.6374 11.2526 21.4481 11.25 21.25V19.75C11.25 19.5511 11.329 19.3603 11.4697 19.2197C11.6103 19.079 11.8011 19 12 19C12.1989 19 12.3897 19.079 12.5303 19.2197C12.671 19.3603 12.75 19.5511 12.75 19.75V21.25C12.7474 21.4481 12.6676 21.6374 12.5275 21.7775C12.3874 21.9176 12.1981 21.9974 12 22Z"
          ></path>
          <path
            d="M21.25 12.75H19.75C19.5511 12.75 19.3603 12.671 19.2197 12.5303C19.079 12.3897 19 12.1989 19 12C19 11.8011 19.079 11.6103 19.2197 11.4697C19.3603 11.329 19.5511 11.25 19.75 11.25H21.25C21.4489 11.25 21.6397 11.329 21.7803 11.4697C21.921 11.6103 22 11.8011 22 12C22 12.1989 21.921 12.3897 21.7803 12.5303C21.6397 12.671 21.4489 12.75 21.25 12.75Z"
          ></path>
          <path
            d="M4.25 12.75H2.75C2.55109 12.75 2.36032 12.671 2.21967 12.5303C2.07902 12.3897 2 12.1989 2 12C2 11.8011 2.07902 11.6103 2.21967 11.4697C2.36032 11.329 2.55109 11.25 2.75 11.25H4.25C4.44891 11.25 4.63968 11.329 4.78033 11.4697C4.92098 11.6103 5 11.8011 5 12C5 12.1989 4.92098 12.3897 4.78033 12.5303C4.63968 12.671 4.44891 12.75 4.25 12.75Z"
          ></path>
          <path
            d="M6.50001 7.24995C6.30707 7.2352 6.12758 7.14545 6.00001 6.99995L4.91001 5.99995C4.83844 5.92838 4.78167 5.84341 4.74293 5.7499C4.7042 5.65639 4.68427 5.55617 4.68427 5.45495C4.68427 5.35373 4.7042 5.25351 4.74293 5.16C4.78167 5.06649 4.83844 4.98152 4.91001 4.90995C4.98158 4.83838 5.06655 4.78161 5.16006 4.74287C5.25357 4.70414 5.3538 4.6842 5.45501 4.6842C5.55623 4.6842 5.65645 4.70414 5.74996 4.74287C5.84347 4.78161 5.92844 4.83838 6.00001 4.90995L7.00001 5.99995C7.123 6.13746 7.19099 6.31547 7.19099 6.49995C7.19099 6.68443 7.123 6.86244 7.00001 6.99995C6.87244 7.14545 6.69295 7.2352 6.50001 7.24995Z"
          ></path>
          <path
            d="M18.56 19.31C18.4615 19.3104 18.3638 19.2912 18.2728 19.2534C18.1818 19.2157 18.0993 19.1601 18.03 19.09L17 18C16.9332 17.86 16.9114 17.7028 16.9376 17.5499C16.9638 17.3971 17.0368 17.2561 17.1465 17.1464C17.2561 17.0368 17.3971 16.9638 17.55 16.9376C17.7028 16.9113 17.8601 16.9331 18 17L19.09 18C19.2305 18.1406 19.3094 18.3312 19.3094 18.53C19.3094 18.7287 19.2305 18.9194 19.09 19.06C19.0233 19.1355 18.9419 19.1967 18.8508 19.2397C18.7597 19.2827 18.6607 19.3066 18.56 19.31Z"
          ></path>
          <path
            d="M17.5 7.24995C17.3071 7.2352 17.1276 7.14545 17 6.99995C16.877 6.86244 16.809 6.68443 16.809 6.49995C16.809 6.31547 16.877 6.13746 17 5.99995L18 4.90995C18.1445 4.76541 18.3406 4.6842 18.545 4.6842C18.7494 4.6842 18.9455 4.76541 19.09 4.90995C19.2345 5.05449 19.3158 5.25054 19.3158 5.45495C19.3158 5.65936 19.2345 5.85541 19.09 5.99995L18 6.99995C17.8724 7.14545 17.6929 7.2352 17.5 7.24995Z"
          ></path>
          <path
            d="M5.44001 19.31C5.34147 19.3104 5.24383 19.2912 5.15282 19.2534C5.06181 19.2157 4.97926 19.1601 4.91001 19.09C4.76956 18.9494 4.69067 18.7587 4.69067 18.56C4.69067 18.3612 4.76956 18.1706 4.91001 18.03L6.00001 17C6.13997 16.9331 6.2972 16.9113 6.45006 16.9376C6.60293 16.9638 6.7439 17.0368 6.85357 17.1464C6.96324 17.2561 7.03621 17.3971 7.06244 17.5499C7.08866 17.7028 7.06685 17.86 7.00001 18L6.00001 19.09C5.92728 19.1638 5.83985 19.2216 5.74338 19.2595C5.64691 19.2974 5.54356 19.3146 5.44001 19.31Z"
          ></path>
        </g>
      </svg>
    </label>
    <v-spacer></v-spacer>
    <div class="tabs hidden-sm hidden-xs">
      <!-- <button v-for="link in links" :key="link" class="tabs2 mx-5">
        {{ link }}
      </button> -->
      <button class="tabs2 mx-5">لیست اطلاعات</button>
      <router-link to="/tahlil" custom v-slot="{ navigate }">
        <button @click="navigate" role="link" class="tabs2 mx-5">
          سازمان ها
        </button>
      </router-link>
      <button class="tabs2 mx-5">تحلیل اطلاعات</button>
      <router-link to="/homee" custom v-slot="{ navigate }">
        <button @click="navigate" role="link" class="tabs2 mx-5">
          نمای کلی
        </button>
      </router-link>
    </div>
    <DropDown class="dropD" />
    <div class="webName">
      <span class="subtitl">سامانه رهگیری</span>
      <v-avatar size="50">
        <v-img src="../../src/assets/lgo.png"></v-img>
      </v-avatar>
    </div>
  </v-app-bar>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");

.dropD {
  opacity: 0;
  visibility: hidden;
  display: inline-block;
  width: 0%;
}
@media (max-width: 960px) {
  .dropD {
    opacity: 1;
    visibility: visible;
    width: auto;
    transition: all 0.3s ease;
  }
}
.subtitl {
  font-size: 18px;
  font-weight: 600;
  color: #36597d;
  cursor: default;
  padding-left: 5px;
}
.webName {
  border: 2px solid #36597d;
  border-radius: 15px;
}
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
  font-size: 17px;
  font-weight: bold;
  position: relative;
  text-decoration: none;
  padding-bottom: 18px;
  transition: all 0.5s ease;
}
@media (max-width: 1045px) {
  .tabs2 {
    font-size: 14px;
    transition: all 0.5s ease;
  }
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
  transition: transform 0.5s ease-in-out;
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
  transition: 0.5s;
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
  transition: 0.5s;
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
  width: 50%;
} */
.lab2 svg {
  position: absolute;
  top: 5px;
  z-index: 100;
}
.lab2 svg.sun {
  left: 5px;
  fill: #fff;
  transition: 0.5s;
}
.lab2 svg.moon {
  left: 50px;
  fill: #7e7e7e;
  transition: 0.5s;
}
.in2:checked + .lab2 svg.sun {
  fill: #7e7e7e;
}
.in2:checked + .lab2 svg.moon {
  fill: #fff;
}
</style>
<style src="vue-multiselect/dist/vue-multiselect.css"></style>

<script>
import DropDown from "./Drop-Down.vue";

export default {
  components: { DropDown },
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
