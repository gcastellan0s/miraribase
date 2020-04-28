<template>
  <div class="kt-widget14">
    <div class="kt-widget14__header">
      <h3 class="kt-widget14__title">
        Revenue Change
      </h3>
      <span class="kt-widget14__desc">
        Revenue change breakdown by cities
      </span>
    </div>
    <div class="kt-widget14__content">
      <div class="kt-widget14__chart">
        <div class="kt-widget14__stat">45</div>
        <Chart1
          ref="chart"
          v-bind:options="chartOptions"
          height="150"
          width="150"
        ></Chart1>
      </div>
      <div class="kt-widget14__legends">
        <div class="kt-widget14__legend">
          <span class="kt-widget14__bullet kt-bg-success"></span>
          <span class="kt-widget14__stats">+10% New York</span>
        </div>
        <div class="kt-widget14__legend">
          <span class="kt-widget14__bullet kt-bg-warning"></span>
          <span class="kt-widget14__stats">-7% London</span>
        </div>
        <div class="kt-widget14__legend">
          <span class="kt-widget14__bullet kt-bg-brand"></span>
          <span class="kt-widget14__stats">+20% California</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Chart1 from "@/views/partials/widgets/Chart1.vue";

export default {
  name: "widget-14-3",
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
    this.chartOptions = {
      type: "doughnut",
      data: {
        datasets: [
          {
            data: [35, 30, 35],
            backgroundColor: [
              this.layoutConfig("colors.state.success"),
              this.layoutConfig("colors.state.danger"),
              this.layoutConfig("colors.state.brand")
            ]
          }
        ],
        labels: ["New York", "London", "California"]
      },
      options: {
        cutoutPercentage: 75,
        responsive: true,
        maintainAspectRatio: false,
        legend: {
          display: false,
          position: "top"
        },
        title: {
          display: false,
          text: "Technology"
        },
        animation: {
          animateScale: true,
          animateRotate: true
        },
        tooltips: {
          enabled: true,
          intersect: false,
          mode: "nearest",
          bodySpacing: 5,
          yPadding: 10,
          xPadding: 10,
          caretPadding: 0,
          displayColors: false,
          backgroundColor: this.layoutConfig("colors.state.brand"),
          titleFontColor: "#ffffff",
          cornerRadius: 4,
          footerSpacing: 0,
          titleSpacing: 0
        }
      }
    };
  },
  computed: {
    ...mapGetters(["layoutConfig"])
  }
};
</script>
