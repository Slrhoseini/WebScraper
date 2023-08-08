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
    <v-card class="rounded-xl mx-auto mb-5" variant="outlined" width="500">
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
        <v-table>
          <thead class="tabl">
            <tr>
              <th class="text-left">Name</th>
              <th class="text-left">Calories</th>
            </tr>
          </thead>
          <p class="unBlurText text-right">
            برای دیدن لیست سازمان ها کلیک کنید
          </p>
          <tbody class="tabl">
            <tr v-for="item in desserts" :key="item.name">
              <td>{{ item.name }}</td>
              <td>{{ item.calories }}</td>
            </tr>
          </tbody>
        </v-table>
      </v-card-item></v-card
    >
  </v-row>
</template>

<script>
import Chart from "chart.js";

export default {
  data() {
    return {
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
.tabl {
  filter: blur(4px);
}
.unBlurText {
  font-family: Vazirmatn, sans-serif;
  font-size: 17px;
  font-weight: bold;
  text-decoration: none;
  transition: all 0.5s ease;
  cursor: pointer;
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
