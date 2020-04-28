<template>
  <canvas ref="chart"></canvas>
</template>

<script>
import { mapGetters } from "vuex";
import Chart from "chart.js";

export default {
  name: "chart-1",
  components: {},
  props: {
    options: Object
  },
  mounted() {
    setTimeout(() => this.initChart());
  },
  computed: {
    ...mapGetters(["layoutConfig"])
  },
  methods: {
    /**
     * For more chart.js options, please refer to the documentation
     * https://www.chartjs.org/docs/latest/
     */
    initChart() {
      const ctx = this.$refs["chart"].getContext("2d");

      const gradient = ctx.createLinearGradient(0, 0, 0, 240);
      gradient.addColorStop(
        0,
        Chart.helpers
          .color("#e14c86")
          .alpha(1)
          .rgbString()
      );
      gradient.addColorStop(
        1,
        Chart.helpers
          .color("#e14c86")
          .alpha(0.3)
          .rgbString()
      );

      const defaults = {
        type: "line",
        data: {
          labels: [],
          datasets: [
            {
              pointBackgroundColor: Chart.helpers
                .color("#000000")
                .alpha(0)
                .rgbString(),
              pointBorderColor: Chart.helpers
                .color("#000000")
                .alpha(0)
                .rgbString(),
              pointHoverBackgroundColor: this.layoutConfig(
                "colors.state.light"
              ),
              pointHoverBorderColor: Chart.helpers
                .color("#ffffff")
                .alpha(0.1)
                .rgbString()
            }
          ]
        },
        options: {
          title: {
            display: false
          },
          tooltips: {
            mode: "nearest",
            intersect: false,
            position: "nearest",
            xPadding: 10,
            yPadding: 10,
            caretPadding: 10
          },
          legend: {
            display: false
          },
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            xAxes: [
              {
                display: false,
                gridLines: false,
                scaleLabel: {
                  display: true,
                  labelString: "Month"
                }
              }
            ],
            yAxes: [
              {
                display: false,
                gridLines: false,
                scaleLabel: {
                  display: true,
                  labelString: "Value"
                },
                ticks: {
                  beginAtZero: true
                }
              }
            ]
          },
          elements: {
            line: {
              tension: 0.0000001
            },
            point: {
              radius: 4,
              borderWidth: 12
            }
          },
          layout: {
            padding: {
              left: 0,
              right: 0,
              top: 10,
              bottom: 0
            }
          }
        }
      };

      let config = Object.assign({}, defaults, this.options);

      new Chart(ctx, config);
    }
  }
};
</script>
