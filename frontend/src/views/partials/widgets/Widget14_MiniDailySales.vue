<template>
  <div class="kt-widget14">
    <div class="kt-widget14__header kt-margin-b-30">
      <h3 class="kt-widget14__title">
        Daily Sales
      </h3>
      <span class="kt-widget14__desc">
        Check out each collumn for more details
      </span>
    </div>
    <div class="kt-widget14__chart">
      <Chart1 ref="chart" v-bind:options="chartOptions"></Chart1>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Chart1 from "@/views/partials/widgets/Chart1.vue";

export default {
  name: "widget-14-1",
  components: {
    Chart1
  },
  data() {
    return {
      chartOptions: {}
    };
  },
  props: {
    title: String,
    desc: String
  },
  mounted() {
    const chartData = {
      labels: [
        "Label 1",
        "Label 2",
        "Label 3",
        "Label 4",
        "Label 5",
        "Label 6",
        "Label 7",
        "Label 8",
        "Label 9",
        "Label 10",
        "Label 11",
        "Label 12",
        "Label 13",
        "Label 14",
        "Label 15",
        "Label 16"
      ],
      datasets: [
        {
          //label: 'Dataset 1',
          backgroundColor: this.layoutConfig("colors.state.success"),
          data: [15, 20, 25, 30, 25, 20, 15, 20, 25, 30, 25, 20, 15, 10, 15, 20]
        },
        {
          //label: 'Dataset 2',
          backgroundColor: "#f3f3fb",
          data: [15, 20, 25, 30, 25, 20, 15, 20, 25, 30, 25, 20, 15, 10, 15, 20]
        }
      ]
    };
    this.chartOptions = {
      type: "bar",
      data: chartData,
      options: {
        title: {
          display: false
        },
        tooltips: {
          intersect: false,
          mode: "nearest",
          xPadding: 10,
          yPadding: 10,
          caretPadding: 10
        },
        legend: {
          display: false
        },
        responsive: true,
        maintainAspectRatio: false,
        barRadius: 4,
        scales: {
          xAxes: [
            {
              display: false,
              gridLines: false,
              stacked: true
            }
          ],
          yAxes: [
            {
              display: false,
              stacked: true,
              gridLines: false
            }
          ]
        },
        layout: {
          padding: {
            left: 0,
            right: 0,
            top: 0,
            bottom: 0
          }
        }
      }
    };
  },
  computed: {
    ...mapGetters(["layoutConfig"])
  }
};
</script>
