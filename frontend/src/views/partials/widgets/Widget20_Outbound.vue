<template>
  <div class="kt-widget20">
    <div class="kt-widget20__content kt-portlet__space-x">
      <span class="kt-widget20__number kt-font-brand">{{ title }}</span>
      <span class="kt-widget20__desc">{{ desc }}</span>
    </div>
    <div class="kt-widget20__chart" style="height:130px;">
      <Chart1 ref="chart" v-bind:options="chartOptions"></Chart1>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Chart from "chart.js";
import Chart1 from "@/views/partials/widgets/Chart1.vue";

export default {
  name: "widget-20",
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
    const ctx = this.$refs["chart"].$el.getContext("2d");

    var gradient = ctx.createLinearGradient(0, 0, 0, 240);
    gradient.addColorStop(
      0,
      Chart.helpers
        .color("#ffefce")
        .alpha(1)
        .rgbString()
    );
    gradient.addColorStop(
      1,
      Chart.helpers
        .color("#ffefce")
        .alpha(0.3)
        .rgbString()
    );

    const defaults = {
      data: {
        labels: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October"
        ],
        datasets: [
          {
            label: "Bandwidth Stats",
            backgroundColor: gradient,
            borderColor: this.layoutConfig("colors.state.warning"),
            pointBackgroundColor: Chart.helpers
              .color("#000000")
              .alpha(0)
              .rgbString(),
            pointBorderColor: Chart.helpers
              .color("#000000")
              .alpha(0)
              .rgbString(),
            pointHoverBackgroundColor: this.layoutConfig("colors.state.danger"),
            pointHoverBorderColor: Chart.helpers
              .color("#000000")
              .alpha(0.1)
              .rgbString(),
            data: [10, 14, 12, 16, 9, 11, 13, 9, 13, 15]
          }
        ]
      }
    };

    this.chartOptions = Object.assign({}, defaults, this.chartOptions);
  },
  computed: {
    ...mapGetters(["layoutConfig"])
  },
  methods: {}
};
</script>
