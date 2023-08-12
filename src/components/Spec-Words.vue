<template>
  <v-dialog v-model="dialog" width="800px">
    <template v-slot:activator="{ props }">
      <v-btn color="blue" v-bind="props" class="mb-4"> تست سازمان </v-btn>
    </template>
    <v-toolbar flat color="white">
      <v-spacer></v-spacer>
      <v-btn
        class="subbtn"
        color="white"
        size="large"
        :style="{ backgroundColor: showData === 3 ? '#0080ff' : 'gray' }"
      >
        اطلاعات منتشر شده
      </v-btn>
      /
      <v-btn
        class="subbtn"
        color="white"
        size="large"
        v-on:click="showData = 2"
        :style="{ backgroundColor: showData === 2 ? '#0080ff' : 'gray' }"
      >
        اطلاعات سازمان
      </v-btn>

      /
      <v-btn
        class="subbtn"
        color="white"
        size="large"
        v-on:click="showData = 1"
        :style="{ backgroundColor: showData === 1 ? '#0080ff' : 'gray' }"
      >
        لیست سازمان ها</v-btn
      >
    </v-toolbar>
    <v-card v-if="showData === 1">
      <v-table>
        <thead>
          <tr>
            <th class="text-left">کشور</th>
            <th class="text-left">اطلاعات منتشر شده</th>
            <th class="text-left">کلمات کلیدی</th>
            <th class="text-left">حوزه فعالیت</th>
            <th class="text-left">نام سازمان/سایت</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in desserts" :key="item.name">
            <td>{{ item.name }}</td>
            <td>{{ item.num }}</td>
            <td>{{ item.word }}</td>
            <td>{{ item.area }}</td>
            <td>{{ item.site }}</td>
          </tr>
        </tbody>
      </v-table>
    </v-card>
    <v-card v-if="showData === 2" class="mx-auto">
      <v-card-item>
        <div>
          <div class="head1">
            www.example.com
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            :نام سازمان / سایت
          </div>
          <div class="subhead1">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aperiam
            maxime eveniet recusandae quis velit nesciunt similique obcaecati
            nihil neque iusto fugiat, accusamus harum! Asperiores alias omnis ut
            impedit, ab nostrum.
          </div>
          <div class="head1">
            USA
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            :کشور
          </div>
          <div class="head1">
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            :حوزه فعالیت
          </div>
          <div class="subhead1">
            لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ، و با
            استفاده از طراحان گرافیک است، چاپگرها و متون بلکه روزنامه و مجله در
            ستون و سطرآنچنان که لازم است، و برای شرایط فعلی تکنولوژی مورد نیاز،
            و کاربردهای متنوع با هدف بهبود ابزارهای کاربردی می باشد، کتابهای
            زیادی در شصت و سه درصد گذشته حال و آینده، شناخت فراوان جامعه و
            متخصصان را می طلبد.
          </div>
          <div class="head1">
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            :کلمات کلیدی
          </div>
        </div>
      </v-card-item>
      <v-card-actions class="cardbtns">
        <v-btn variant="outlined"> Keyword </v-btn>
        <v-btn variant="outlined"> Keyword </v-btn>
        <v-btn variant="outlined"> Keyword </v-btn>
        <v-btn variant="outlined"> Keyword </v-btn>
      </v-card-actions>
      <v-card class="barcard rounded-xl mb-5" variant="outlined">
        <v-card-item class="pa-0">
          <!-- <v-col>
            <v-row class="rowback pa-2">
              <v-btn icon variant="text" size="30">
                <v-icon color="#fff">mdi-download</v-icon>
              </v-btn>
              <v-btn icon variant="text" size="30">
                <v-icon color="#fff">mdi-fullscreen</v-icon>
              </v-btn>
              <v-spacer></v-spacer>
              <p class="ptag">انتشار بر اساس سال</p>
            </v-row>
          </v-col> -->
          <dChart /> </v-card-item
      ></v-card>
    </v-card>
  </v-dialog>
</template>

<script>
import dChart from "./Dialog-Chart.vue";
export default {
  components: {
    dChart,
  },
  data() {
    return {
      hasSaved: false,
      dialog: false,
      showData: 1,
      isEditing: null,
      selected: [],
      desserts: [
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
        {
          name: "USA",
          num: "۸۵۰۰",
          word: "Data mining   Laser",
          area: "technology",
          site: "www.example.com",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
* {
  font-family: Vazirmatn, sans-serif;
}
.p {
  font-family: Vazirmatn, sans-serif;
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
.addbtn {
  align-self: center;
  color: white !important;
}
.subbtn {
  align-self: center;
  /* background-color: #36597d !important; */
  margin: 5px;
  border-radius: 30px;
  transition: all 0.3s ease-in-out;
}
.head1 {
  font-weight: bold;
  margin-bottom: 5px;
}
.subhead1 {
  font-size: 14px;
  margin-bottom: 5px;
}
.cardbtns {
  margin-left: auto;
}
.barcard {
  margin: auto;
}
</style>
