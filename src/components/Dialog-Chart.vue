<template>
  <div class="chart2">
    <canvas ref="barChartCanvas" width="400" height="270"></canvas>
  </div>
  <div>
    <canvas ref="bubbleChartCanvas"></canvas>
  </div>
  <div>
    <canvas ref="areaChartCanvas"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js";

export default {
  mounted() {
    this.drawBarChart();
    this.drawBubbleChart();
    this.drawAreaChart();
  },
  methods: {
    drawBarChart() {
      const ctx = this.$refs.barChartCanvas.getContext("2d");
      new Chart(ctx, {
        type: "bar",
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
              backgroundColor: "rgb(75, 192, 192)",
              borderColor: "rgb(75, 192, 192)",
              borderWidth: 1,
            },
          ],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            x: {
              display: true,
              title: {
                display: true,
                text: "Month",
              },
            },
            y: {
              display: true,
              title: {
                display: true,
                text: "Value",
              },
            },
          },
        },
      });
    },
    drawBubbleChart() {
      const ctx = this.$refs.bubbleChartCanvas.getContext("2d");
      new Chart(ctx, {
        type: "bubble",
        data: {
          datasets: [
            {
              label: "Dataset 1",
              data: [
                { x: 10, y: 20, r: 5 },
                { x: 15, y: 10, r: 10 },
                { x: 30, y: 25, r: 7 },
              ],
              backgroundColor: "rgba(255, 99, 132, 0.6)",
            },
          ],
        },
        options: {
          scales: {
            x: {
              min: 0,
              max: 40,
            },
            y: {
              min: 0,
              max: 30,
            },
          },
        },
      });
    },
    drawAreaChart() {
      const ctx = this.$refs.areaChartCanvas.getContext("2d");
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
              label: "Dataset 1",
              data: [0, 10, 5, 2, 20, 30, 45],
              borderColor: "rgba(75, 192, 192, 1)",
              backgroundColor: "rgba(75, 192, 192, 0.2)",
              tension: 0.4,
              fill: true,
            },
          ],
        },
        options: {
          scales: {
            x: {
              beginAtZero: true,
            },
            y: {
              beginAtZero: true,
            },
          },
        },
      });
    },
  },
};
</script>
