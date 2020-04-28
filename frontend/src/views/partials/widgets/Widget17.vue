<template>
  <div class="kt-widget17">
    <div
      class="kt-widget17__visual kt-widget17__visual--chart kt-portlet-fit--top kt-portlet-fit--sides"
      style="background-color: #fd397a"
    >
      <div class="kt-widget17__chart" style="height:320px;">
        <Chart1 ref="chart" v-bind:options="chartOptions"></Chart1>
      </div>
    </div>
    <div class="kt-widget17__stats">
      <div class="kt-widget17__items">
        <div class="kt-widget17__item">
          <span class="kt-widget17__icon">
            <img
              svg-inline
              class="kt-svg-icon kt-svg-icon--brand"
              src="@/assets/media/icons/svg/Home/Library.svg"
              alt=""
            />
          </span>
          <span class="kt-widget17__subtitle">
            Delivered
          </span>
          <span class="kt-widget17__desc">
            15 New Paskages
          </span>
        </div>

        <div class="kt-widget17__item">
          <span class="kt-widget17__icon">
            <img
              svg-inline
              class="kt-svg-icon kt-svg-icon--success"
              src="@/assets/media/icons/svg/Design/Layers.svg"
              alt=""
          /></span>
          <span class="kt-widget17__subtitle">
            Ordered
          </span>
          <span class="kt-widget17__desc">
            72 New Items
          </span>
        </div>
      </div>
      <div class="kt-widget17__items">
        <div class="kt-widget17__item">
          <span class="kt-widget17__icon">
            <img
              svg-inline
              class="kt-svg-icon kt-svg-icon--warning"
              src="@/assets/media/icons/svg/Communication/Urgent-mail.svg"
              alt=""
          /></span>
          <span class="kt-widget17__subtitle">
            Reported
          </span>
          <span class="kt-widget17__desc">
            72 Support Cases
          </span>
        </div>

        <div class="kt-widget17__item">
          <span class="kt-widget17__icon">
            <img
              svg-inline
              class="kt-svg-icon kt-svg-icon--danger"
              src="@/assets/media/icons/svg/Design/PenAndRuller.svg"
              alt=""
          /></span>
          <span class="kt-widget17__subtitle">
            Arrived
          </span>
          <span class="kt-widget17__desc">
            34 Upgraded Boxes
          </span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import Chart from "chart.js";
import Chart1 from "@/views/partials/widgets/Chart1.vue";

export default {
  name: "widget-17",
  components: {
    Chart1
  },
  data() {
    return {
      chartOptions: {}
    };
  },
  mounted() {
    this.chartOptions = {
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
            label: "Sales Stats",
            backgroundColor: Chart.helpers
              .color("#e14c86")
              .alpha(1)
              .rgbString(),
            borderColor: "#e13a58",
            pointBackgroundColor: Chart.helpers
              .color("#000000")
              .alpha(0)
              .rgbString(),
            pointBorderColor: Chart.helpers
              .color("#000000")
              .alpha(0)
              .rgbString(),
            pointHoverBackgroundColor: this.layoutConfig("colors.state.light"),
            pointHoverBorderColor: Chart.helpers
              .color("#ffffff")
              .alpha(0.1)
              .rgbString(),
            data: [10, 14, 12, 16, 9, 11, 13, 9, 13, 15]
          }
        ]
      }
    };
  },
  computed: {
    ...mapGetters(["layoutConfig"])
  }
};
</script>
