<template>
  <v-app id="inspire">
    <Header />
    <SubHeader />
    <template v-slot:activator="{ props }">
      <v-btn color="blue" v-bind="props" class="mb-4"> تست سازمان </v-btn>
    </template>
    <v-container>
      <v-toolbar flat color="white" class="tool1">
        <v-spacer></v-spacer>
        <v-btn
          class="subbtn"
          color="white"
          size="large"
          v-on:click="showData = 3"
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
        <v-row>
          <v-col>
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
                <dChart />
              </v-card-item>
            </v-card>
          </v-col>
          <v-col>
            <v-card>
              <v-card-item>
                <div>
                  <div class="head11">
                    <div class="head12">www.example.com</div>
                    <div class="head13">: نام سازمان / سایت</div>
                  </div>
                  <div class="subhead1">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                    Aperiam maxime eveniet recusandae quis velit nesciunt
                    similique obcaecati nihil neque iusto fugiat, accusamus
                    harum! Asperiores alias omnis ut impedit, ab nostrum.
                  </div>
                  <div class="head11">
                    <div class="head12">USA</div>
                    <div class="head13">: کشور</div>
                  </div>
                  <div class="head11">
                    <div class="head131">: حوزه فعالیت</div>
                  </div>
                  <div class="subhead2">
                    لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ، و
                    با استفاده از طراحان گرافیک است، چاپگرها و متون بلکه روزنامه
                    و مجله در ستون و سطرآنچنان که لازم است، و برای شرایط فعلی
                    تکنولوژی مورد نیاز، و کاربردهای متنوع با هدف بهبود ابزارهای
                    کاربردی می باشد، کتابهای زیادی در شصت و سه درصد گذشته حال و
                    آینده، شناخت فراوان جامعه و متخصصان را می طلبد
                  </div>
                  <div class="head11">
                    <div class="head131">: کلمات کلیدی</div>
                  </div>
                </div>
                <v-card-actions class="cardbtns">
                  <v-btn variant="outlined"> Keyword </v-btn>
                  <v-btn variant="outlined"> Keyword </v-btn>
                  <v-btn variant="outlined"> Keyword </v-btn>
                  <v-btn variant="outlined"> Keyword </v-btn>
                </v-card-actions>
              </v-card-item>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
      <v-card v-if="showData === 3" class="mx-auto">
        <v-row>
          <v-col>
            <v-card>
              <v-card-item>
                <div>
                  <div class="head11">
                    <div class="head12">
                      <v-icon
                        color="blue-darken-2"
                        icon="mdi-file-document-outline"
                      ></v-icon>
                      News
                    </div>
                    <div class="head132">www.example.com</div>
                  </div>
                  <div class="head11">
                    <div class="head12">Lorem ipsum dolor sit amet</div>
                    <div class="head13">: عنوان</div>
                  </div>
                  <div class="head11">
                    <div class="head12">www.example.com/admin/url</div>
                    <div class="head13">: لینک مرتبط</div>
                  </div>
                  <div class="head11">
                    <div class="head131">: متن اصلی</div>
                    <div class="subhead1">
                      Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                      Aperiam maxime eveniet recusandae quis velit nesciunt
                      similique obcaecati nihil neque iusto fugiat, accusamus
                      harum! Asperiores alias omnis ut impedit, ab nostrum.
                      Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                      Voluptates praesentium incidunt placeat facere nam optio
                      totam consequatur! Odit magni sapiente molestias cum,
                      expedita ipsum, nemo illo perferendis exercitationem ullam
                      blanditiis. Lorem ipsum dolor sit amet consectetur
                      adipisicing elit. Dolorum corporis placeat ducimus. Dicta
                      tenetur quo reiciendis laboriosam labore illum quas
                      asperiores tempore eius consectetur. Ratione dolor ea
                      nihil maiores unde? Lorem, ipsum dolor sit amet
                      consectetur adipisicing elit. Dolorem veniam laudantium
                      animi mollitia nemo voluptates iusto rerum laboriosam
                      fugiat neque? Saepe nam id voluptate consectetur. Ducimus
                      voluptatum ut necessitatibus inventore. Lorem ipsum dolor
                      sit amet consectetur adipisicing elit. Provident illo
                      inventore laudantium veniam maiores repellendus ab
                      temporibus consequatur, libero amet consectetur qui a,
                      dolorem ea molestiae. Numquam distinctio temporibus enim.
                      Lorem ipsum dolor sit amet consectetur adipisicing elit.
                    </div>
                  </div>
                </div>
              </v-card-item>
            </v-card>
          </v-col>
          <v-col>
            <v-card>
              <v-card-item>
                <div>
                  <div class="head11">
                    <div class="head12">Lorem ipsum dolor sit amet</div>
                    <div class="head13">: عنوان</div>
                  </div>
                  <div class="subhead1">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. A,
                    illo, provident nam est recusandae libero sequi, qui dolor
                    officiis temporibus animi rerum? Tempora vero totam, quae
                    assumenda in aliquam obcaecati.
                  </div>
                  <div class="head11">
                    <div class="head121">
                      <v-icon
                        color="blue-darken-2"
                        icon="mdi-file-document-outline"
                      ></v-icon>
                      News
                    </div>
                    <div class="head11">
                      <div class="head12">www.example.com/admin/url</div>
                      <div class="head13">: لینک مرتبط</div>
                    </div>
                  </div>
                  <v-card-actions class="cardbtns">
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                  </v-card-actions>
                </div>
              </v-card-item>
              <v-divider></v-divider>
              <v-card-item>
                <div>
                  <div class="head11">
                    <div class="head12">Lorem ipsum dolor sit amet</div>
                    <div class="head13">: عنوان</div>
                  </div>
                  <div class="subhead1">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. A,
                    illo, provident nam est recusandae libero sequi, qui dolor
                    officiis temporibus animi rerum? Tempora vero totam, quae
                    assumenda in aliquam obcaecati.
                  </div>
                  <div class="head11">
                    <div class="head121">
                      <v-icon
                        color="blue-darken-2"
                        icon="mdi-file-document-outline"
                      ></v-icon>
                      News
                    </div>
                    <div class="head11">
                      <div class="head12">www.example.com/admin/url</div>
                      <div class="head13">: لینک مرتبط</div>
                    </div>
                  </div>
                  <v-card-actions class="cardbtns">
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                  </v-card-actions>
                </div>
              </v-card-item>
              <v-divider></v-divider>
              <v-card-item>
                <div>
                  <div class="head11">
                    <div class="head12">Lorem ipsum dolor sit amet</div>
                    <div class="head13">: عنوان</div>
                  </div>
                  <div class="subhead1">
                    Lorem ipsum, dolor sit amet consectetur adipisicing elit. A,
                    illo, provident nam est recusandae libero sequi, qui dolor
                    officiis temporibus animi rerum? Tempora vero totam, quae
                    assumenda in aliquam obcaecati.
                  </div>
                  <div class="head11">
                    <div class="head121">
                      <v-icon
                        color="blue-darken-2"
                        icon="mdi-file-document-outline"
                      ></v-icon>
                      News
                    </div>
                    <div class="head11">
                      <div class="head12">www.example.com/admin/url</div>
                      <div class="head13">: لینک مرتبط</div>
                    </div>
                  </div>
                  <v-card-actions class="cardbtns">
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                    <v-btn variant="outlined"> Keyword </v-btn>
                  </v-card-actions>
                </div>
              </v-card-item>
            </v-card>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>
import dChart from "./Dialog-Chart.vue";
import Header from "../components/Head-er.vue";
import SubHeader from "../components/Sub-Header.vue";
export default {
  components: {
    dChart,
    Header,
    SubHeader,
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
.subhead2 {
  font-size: 14px;
  margin-bottom: 5px;
  text-align: right;
}
.cardbtns {
  margin-left: auto;
  float: right;
}
.barcard {
  margin: auto;
}
.tool1 {
  margin-top: 65px;
}
.head11 {
  width: 100%;
}
.head12 {
  font-weight: bold;
  margin-bottom: 10px;
  width: 50%;
  float: left;
}
.head13 {
  font-weight: bold;
  margin-bottom: 10px;
  width: 50%;
  float: left;
  text-align: right;
}
.head131 {
  font-weight: bold;
  margin-bottom: 5px;
  width: 100%;
  float: right;
  text-align: right;
}
.head132 {
  font-weight: bold;
  margin-bottom: 11px;
  width: 50%;
  float: left;
  text-align: right;
}
.head121 {
  font-weight: bold;
  margin-bottom: 5px;
  width: 100%;
  float: left;
}
</style>
