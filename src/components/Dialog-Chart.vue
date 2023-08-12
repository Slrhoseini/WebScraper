<template>
  <div class="chart2">
    <canvas ref="barChartCanvas" width="400" height="270"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js";

export default {
  mounted() {
    this.drawBarChart();
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
  },
};
</script>
