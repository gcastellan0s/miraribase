<template>
  <div>
    <div class="row">
      <div class="col-lg-6 col-xl-4 order-lg-1 order-xl-1">
        <!--begin:: Widgets/Activity-->
        <KTPortlet
          v-bind="{
            title: 'Activity',
            class: 'kt-portlet--fit kt-portlet--skin-solid',
            headClass: 'kt-portlet__head--noborder kt-portlet__space-x',
            headSize: 'lg',
            fluidHeight: true,
            headOverlay: true,
            headNoBorder: true
          }"
        >
          <template v-slot:toolbar>
            <a
              href="#"
              class="btn btn-label-light btn-sm btn-bold dropdown-toggle"
              data-toggle="dropdown"
              aria-expanded="false"
            >
              Export
            </a>
            <div class="dropdown-menu dropdown-menu-fit dropdown-menu-right">
              <ContextMenu1></ContextMenu1>
            </div>
          </template>
          <template v-slot:body>
            <Widget17></Widget17>
          </template>
        </KTPortlet>
        <!--end:: Widgets/Activity-->
      </div>

      <div class="col-lg-6 col-xl-4 order-lg-1 order-xl-1">
        <!--begin:: Widgets/Inbound Bandwidth-->
        <KTPortlet
          v-bind="{
            title: 'Inbound Bandwidth',
            class: 'kt-portlet--fit kt-portlet--head-noborder',
            headClass: 'kt-portlet__space-x',
            fluidHalfHeight: true,
            headNoBorder: true,
            bodyFluid: true
          }"
        >
          <template v-slot:toolbar>
            <a
              href="#"
              class="btn btn-label-success btn-sm btn-bold dropdown-toggle"
              data-toggle="dropdown"
              aria-expanded="false"
            >
              Export
            </a>
            <div class="dropdown-menu dropdown-menu-fit dropdown-menu-right">
              <ContextMenu1></ContextMenu1>
            </div>
          </template>
          <template v-slot:body>
            <Widget20_1
              title="670+"
              desc="Successful transactions"
            ></Widget20_1>
          </template>
        </KTPortlet>
        <!--end:: Widgets/Inbound Bandwidth-->
        <div class="kt-space-20"></div>
        <!--begin:: Widgets/Outbound Bandwidth-->
        <KTPortlet
          v-bind="{
            title: 'Outbound Bandwidth',
            class: 'kt-portlet--fit kt-portlet--head-noborder',
            headClass: 'kt-portlet__space-x',
            fluidHalfHeight: true,
            headNoBorder: true,
            bodyFluid: true
          }"
        >
          <template v-slot:toolbar>
            <a
              href="#"
              class="btn btn-label-warning btn-sm btn-bold dropdown-toggle"
              data-toggle="dropdown"
              aria-expanded="false"
            >
              Download
            </a>
            <div class="dropdown-menu dropdown-menu-fit dropdown-menu-right">
              <ContextMenu1></ContextMenu1>
            </div>
          </template>
          <template v-slot:body>
            <Widget20_2 title="1340+" desc="Completed orders"></Widget20_2>
          </template>
        </KTPortlet>
        <!--end:: Widgets/Outbound Bandwidth-->
      </div>

      <div class="col-lg-6 col-xl-4 order-lg-1 order-xl-1">
        <!--Begin::Recent Activities-->
        <KTPortlet v-bind:title="'Recent Activities'">
          <template v-slot:toolbar>
            <div class="dropdown dropdown-inline">
              <button
                type="button"
                class="btn btn-clean btn-sm btn-icon btn-icon-md"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                <i class="flaticon-more-1"></i>
              </button>
              <div
                class="dropdown-menu dropdown-menu-right dropdown-menu-fit dropdown-menu-md"
              >
                <!--begin::Nav-->
                <ContextMenu1></ContextMenu1>
                <!--end::Nav-->
              </div>
            </div>
          </template>
          <template v-slot:body>
            <!--Begin::Timeline 3 -->
            <Timeline2 v-bind:datasrc="timelines"></Timeline2>
            <!--End::Timeline 3 -->
          </template>
        </KTPortlet>
        <!--End::Recent Activities-->
      </div>
    </div>

    <div class="row">
      <div class="col-xl-8 col-lg-12 order-lg-3 order-xl-1">
        <KTPortlet v-bind:title="'Best Sellers'">
          <template v-slot:toolbar>
            <ul
              class="nav nav-pills nav-pills-sm nav-pills-label nav-pills-bold"
              role="tablist"
            >
              <li class="nav-item">
                <a
                  v-on:click="setActiveTab1"
                  data-tab="0"
                  class="nav-link active"
                  data-toggle="tab"
                  href="#"
                  role="tab"
                >
                  Latest
                </a>
              </li>
              <li class="nav-item">
                <a
                  v-on:click="setActiveTab1"
                  data-tab="1"
                  class="nav-link"
                  data-toggle="tab"
                  href="#"
                  role="tab"
                >
                  Month
                </a>
              </li>
              <li class="nav-item">
                <a
                  v-on:click="setActiveTab1"
                  data-tab="2"
                  class="nav-link"
                  data-toggle="tab"
                  href="#"
                  role="tab"
                >
                  All time
                </a>
              </li>
            </ul>
          </template>
          <template v-slot:body>
            <b-tabs class="kt-hide-tabs" v-model="tabIndex">
              <b-tab active>
                <Widget5 v-bind:datasrc="widget5"></Widget5>
              </b-tab>
              <b-tab>
                <Widget5 v-bind:datasrc="widget5"></Widget5>
              </b-tab>
              <b-tab>
                <Widget5 v-bind:datasrc="widget5"></Widget5>
              </b-tab>
            </b-tabs>
          </template>
        </KTPortlet>
      </div>

      <div class="col-xl-4 col-lg-6 order-lg-3 order-xl-1">
        <KTPortlet
          v-bind:title="'New Users'"
          v-bind:class="'kt-portlet--tabs kt-portlet--height-fluid'"
        >
          <template v-slot:toolbar>
            <ul
              class="nav nav-tabs nav-tabs-line nav-tabs-bold nav-tabs-line-brand"
              role="tablist"
            >
              <li class="nav-item">
                <a
                  v-on:click="setActiveTab2"
                  data-tab="0"
                  class="nav-link active"
                  data-toggle="tab"
                  href="#"
                  role="tab"
                >
                  Today
                </a>
              </li>
              <li class="nav-item">
                <a
                  v-on:click="setActiveTab2"
                  data-tab="1"
                  class="nav-link"
                  data-toggle="tab"
                  href="#"
                  role="tab"
                >
                  Month
                </a>
              </li>
            </ul>
          </template>
          <template v-slot:body>
            <b-tabs class="kt-hide-tabs" v-model="tabIndex2">
              <b-tab active>
                <Widget4 v-bind:datasrc="widget4"></Widget4>
              </b-tab>
              <b-tab>
                <Widget4 v-bind:datasrc="widget4"></Widget4>
              </b-tab>
            </b-tabs>
          </template>
        </KTPortlet>
      </div>
    </div>

    <div class="row">
      <div class="col-xl-4 col-lg-4 order-lg-2 order-xl-1">
        <KTPortlet
          v-bind:class="'kt-portlet--height-fluid'"
          v-bind="{ bodyFit: true }"
        >
          <template v-slot:body>
            <Widget14_1></Widget14_1>
          </template>
        </KTPortlet>
      </div>

      <div class="col-xl-4 col-lg-4 order-lg-2 order-xl-1">
        <KTPortlet
          v-bind:class="'kt-portlet--height-fluid'"
          v-bind="{ bodyFit: true }"
        >
          <template v-slot:body>
            <Widget14_2></Widget14_2>
          </template>
        </KTPortlet>
      </div>

      <div class="col-xl-4 col-lg-4 order-lg-2 order-xl-1">
        <KTPortlet
          v-bind:class="'kt-portlet--height-fluid'"
          v-bind="{ bodyFit: true }"
        >
          <template v-slot:body>
            <Widget14_3></Widget14_3>
          </template>
        </KTPortlet>
      </div>
    </div>
  </div>
</template>

<script>
import { SET_BREADCRUMB } from "@/store/breadcrumbs.module";
import KTPortlet from "@/views/partials/content/Portlet.vue";
import ContextMenu1 from "@/views/partials/widgets/ContextMenu1.vue";
import Widget4 from "@/views/partials/widgets/Widget4.vue";
import Widget5 from "@/views/partials/widgets/Widget5.vue";
import Widget14_1 from "@/views/partials/widgets/Widget14_MiniDailySales.vue";
import Widget14_2 from "@/views/partials/widgets/Widget14_MiniProfitShare.vue";
import Widget14_3 from "@/views/partials/widgets/Widget14_MiniRevenueChange.vue";
import Widget17 from "@/views/partials/widgets/Widget17.vue";
import Widget20_1 from "@/views/partials/widgets/Widget20_Inbound.vue";
import Widget20_2 from "@/views/partials/widgets/Widget20_Outbound.vue";
import Timeline2 from "@/views/partials/widgets/Timeline2.vue";

/**
 * Sample widgets data source
 */
import timelines from "@/common/mock/widget-timeline.json";
import widget4 from "@/common/mock/widget-4.json";
import widget5 from "@/common/mock/widget-5.json";

export default {
  name: "dashboard",
  components: {
    KTPortlet,
    ContextMenu1,
    Widget4,
    Widget5,
    Widget14_1,
    Widget14_2,
    Widget14_3,
    Widget17,
    Widget20_1,
    Widget20_2,
    Timeline2
  },
  data() {
    return {
      timelines: timelines,
      widget4: widget4,
      widget5: widget5,
      tabIndex: 0,
      tabIndex2: 0
    };
  },
  mounted() {
    this.$store.dispatch(SET_BREADCRUMB, [{ title: "Dashboard" }]);
  },
  methods: {
    setActiveTab1(event) {
      this.tabIndex = this.setActiveTab(event);
    },
    setActiveTab2(event) {
      this.tabIndex2 = this.setActiveTab(event);
    },
    /**
     * Set current active on click
     * @param event
     */
    setActiveTab(event) {
      // get all tab links
      const tab = event.target.closest('[role="tablist"]');
      const links = tab.querySelectorAll(".nav-link");
      // remove active tab links
      for (let i = 0; i < links.length; i++) {
        links[i].classList.remove("active");
      }

      // set current active tab
      event.target.classList.add("active");

      // set clicked tab index to bootstrap tab
      return parseInt(event.target.getAttribute("data-tab"));
    }
  }
};
</script>
