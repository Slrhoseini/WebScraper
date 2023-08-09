<template>
  <v-row>
    <v-card
      class="vcar1 rounded-xl mb-5"
      variant="outlined"
      width="500"
      height="400"
    >
      <v-card-item class="cardo pa-0">
        <v-col>
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
        </v-col>
        <div class="chart2">
          <canvas ref="lineChartCanvas" width="400" height="350"></canvas>
        </div> </v-card-item
    ></v-card>
    <v-card
      class="vcar2 rounded-xl mb-5"
      variant="outlined"
      width="500"
      height="400"
    >
      <v-card-item class="cardo pa-0">
        <v-col>
          <v-row class="rowback pa-2">
            <v-btn icon variant="text" size="30">
              <v-icon color="#fff">mdi-download</v-icon>
            </v-btn>
            <v-btn icon variant="text" size="30">
              <v-icon color="#fff">mdi-fullscreen</v-icon>
            </v-btn>
            <v-spacer></v-spacer>
            <p class="ptag">انتشار بر اساس منابع</p>
          </v-row>
        </v-col>
        <div class="chart2">
          <canvas ref="pieChartCanvas" width="400" height="350"></canvas>
        </div> </v-card-item
    ></v-card>
  </v-row>
  <v-row>
    <v-card class="rounded-xl mx-auto mb-5" variant="outlined" width="900">
      <v-card-item class="cardo pa-0">
        <v-col>
          <v-row class="rowback pa-2">
            <v-btn icon variant="text" size="30">
              <v-icon color="#fff">mdi-download</v-icon>
            </v-btn>
            <v-btn icon variant="text" size="30">
              <v-icon color="#fff">mdi-fullscreen</v-icon>
            </v-btn>
            <v-spacer></v-spacer>
            <p class="ptag">سازمان ها</p>
          </v-row>
        </v-col>
        <v-container>
          <p
            class="unBlurText"
            @click="handleClick"
            :class="active ? 'active' : 'non-active'"
          >
            برای دیدن لیست سازمان ها کلیک کنید
          </p>
          <v-table class="tabl">
            <thead>
              <tr>
                <th class="text-left">Name</th>
                <th class="text-left">Calories</th>
                <th class="text-left">Name</th>
                <th class="text-left">Calories</th>
                <th class="text-left">Name</th>
                <th class="text-left">Calories</th>
                <th class="text-left">Name</th>
                <th class="text-left">Calories</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in desserts" :key="item.name">
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
                <td>{{ item.name }}</td>
                <td>{{ item.calories }}</td>
              </tr>
            </tbody>
          </v-table>
        </v-container>
      </v-card-item></v-card
    >
  </v-row>
</template>

<script>
import Chart from "chart.js";

export default {
  data() {
    return {
      active: false,
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
        },
        {
          name: "Eclair",
          calories: 262,
        },
        {
          name: "Cupcake",
          calories: 305,
        },
        {
          name: "Gingerbread",
          calories: 356,
        },
        {
          name: "Jelly bean",
          calories: 375,
        },
      ],
    };
  },
  mounted() {
    this.drawLineChart();
    this.drawPieChart();
  },
  methods: {
    handleClick() {
      this.active = !this.active;
    },
    drawLineChart() {
      const ctx = this.$refs.lineChartCanvas.getContext("2d");
      new Chart(ctx, {
        type: "line",
        data: {
          labels: [
            "January",
            "February",
            "March",
            "April",
            "May",
            "June",
            "July",
          ],
          datasets: [
            {
              label: "Example Dataset",
              data: [10, 20, 30, 25, 40, 35, 50],
              borderColor: "rgb(75, 192, 192)",
              borderWidth: 1,
            },
          ],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
        },
      });
    },
    drawPieChart() {
      const ctx = this.$refs.pieChartCanvas.getContext("2d");
      new Chart(ctx, {
        type: "pie",
        data: {
          labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
          datasets: [
            {
              label: "Example Dataset",
              data: [12, 19, 3, 5, 2, 3],
              backgroundColor: [
                "rgb(255, 99, 132)",
                "rgb(54, 162, 235)",
                "rgb(255, 205, 86)",
                "rgb(75, 192, 192)",
                "rgb(153, 102, 255)",
                "rgb(255, 159, 64)",
              ],
              borderWidth: 1,
            },
          ],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
        },
      });
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Vazirmatn&display=swap");
* {
  font-family: Vazirmatn, sans-serif;
}
.active {
  opacity: 0%;
  visibility: hidden;
}
.non-active {
  opacity: 100%;
}
.active + .tabl {
  filter: blur(0px);
}

.tabl {
  filter: blur(3px);
}
.unBlurText {
  font-family: Vazirmatn, sans-serif;
  font-size: 17px;
  font-weight: bold;
  transition: all 0.5s ease;
  cursor: pointer;
  position: absolute;
  z-index: 100;
  text-align: center;
  width: 92%;
  top: 50%;
}
.rowback {
  background-color: #36597d;
}
.ptag {
  color: white;
  font-weight: bold;
}
.vcar1 {
  margin-left: auto;
  margin-right: 10px;
}
.vcar2 {
  margin-right: auto;
  margin-left: 10px;
}
@media (max-width: 1010px) {
  .vcar1 {
    margin-left: 0;
    margin: auto;
  }
  .vcar2 {
    margin-right: 0;
    margin: auto;
  }
}
</style>
