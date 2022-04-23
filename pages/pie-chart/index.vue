<template>
  <div class="chart-container w-4/6">
    <canvas ref="canvas" id="chart" class="m-10 w-full"></canvas>
  </div>
</template>

<script>
import Chart from "chart.js/auto";

export default {
  name: "chart",
  data() {
    return {
      data: {
        type: "doughnut",
        data: {
          labels: [
            "Python",
            "Java",
            "JavaScript",
            "C#",
            "C/C++",
            "PHP",
            "R",
            "TypeScript",
            "Objective-C",
            "Other",
          ],
          datasets: [
            {
              axis: "y",
              label: "Popularity Percentage",
              data: [
                27.95, 18.09, 9.14, 7.39, 7.06, 5.48, 4.41, 2.27, 2.23, 15.98,
              ],
              backgroundColor: [
                "rgba(19, 91, 229, 0.2)",
                "rgba(229, 19, 19, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 159, 64, 0.2)",
                "rgba(41, 213, 219, 0.2)",
                "rgba(217, 41, 219, 0.2)",
                "rgba(84, 219, 41, 0.2)",
                "rgba(8, 8, 8, 0.2)",
              ],
              borderColor: [
                "rgba(19, 91, 229, 1)",
                "rgba(229, 19, 19, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255, 159, 64, 1)",
                "rgba(41, 213, 219, 1)",
                "rgba(217, 41, 219, 1)",
                "rgba(84, 219, 41, 1)",
                "rgba(8, 8, 8, 1)",
              ],
              hoverOffset: 4,
            },
          ],
        },
        options: {
          indexAxis: "y",
          plugins: {
            legend: {
              position: "right",
              labels: {
                padding: 20,
                font: {
                  size: 30,
                },
              },
            },
          },
          animation: {
            duration: 10000,
          },
        },
      },
    };
  },
  mounted() {
    const ctx = this.$refs.canvas.getContext("2d");
    new Chart(ctx, this.data);
  },
};
</script>
