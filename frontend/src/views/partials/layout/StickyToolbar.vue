<template>
  <div>
    <!-- begin::Sticky Toolbar -->
    <ul class="kt-sticky-toolbar" style="margin-top: 30px;">
      <li
        v-b-tooltip.hover.left="'More demos'"
        class="kt-sticky-toolbar__item kt-sticky-toolbar__item--success"
        id="kt_demo_panel_toggle"
      >
        <a href="#"><i class="flaticon2-drop"></i></a>
      </li>
      <li
        v-b-tooltip.hover.left="'Layout builder'"
        class="kt-sticky-toolbar__item kt-sticky-toolbar__item--brand"
      >
        <router-link href="#" :to="{ name: 'builder' }">
          <i class="flaticon2-gear"></i>
        </router-link>
      </li>
      <li
        v-b-tooltip.hover.left="'Documentation'"
        class="kt-sticky-toolbar__item kt-sticky-toolbar__item--warning"
      >
        <a href="https://keenthemes.com/metronic/?page=docs" target="_blank">
          <i class="flaticon2-telegram-logo"></i>
        </a>
      </li>
    </ul>
    <!-- end::Sticky Toolbar -->

    <!-- begin::Demo Panel -->
    <div id="kt_demo_panel" ref="kt_demo_panel" class="kt-demo-panel">
      <div class="kt-demo-panel__head">
        <h3 class="kt-demo-panel__title">
          Select A Demo
        </h3>
        <a href="#" class="kt-demo-panel__close" id="kt_demo_panel_close">
          <i class="flaticon2-delete"></i>
        </a>
      </div>
      <div class="kt-demo-panel__body kt-scroll">
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo1')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo1
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo1.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a
                href="https://keenthemes.com/metronic/preview/vue/demo1"
                class="btn btn-brand btn-elevate"
              >
                Preview
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo2')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 2
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo2.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo3')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 3
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo3.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo4')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 4
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo4.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo5')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 5
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo5.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo6')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 6
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo6.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo7')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 7
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo7.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo8')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 8
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo8.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo9')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 9
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo9.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo10')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 10
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo10.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo11')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 11
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo11.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo12')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 12
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo12.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo13')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 13
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo13.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <div
          class="kt-demo-panel__item"
          v-bind:class="{
            'kt-demo-panel__item--active': isActiveDemo('demo14')
          }"
        >
          <div class="kt-demo-panel__item-title">
            Demo 14
          </div>
          <div class="kt-demo-panel__item-preview">
            <img src="@/assets/media/demos/preview/demo14.jpg" alt="" />
            <div class="kt-demo-panel__item-preview-overlay">
              <a href="#" class="btn btn-brand btn-elevate disabled">
                Coming soon
              </a>
            </div>
          </div>
        </div>
        <a
          href="https://themeforest.net/item/metronic-responsive-admin-dashboard-template/4021469?ref=keenthemes"
          class="kt-demo-panel__purchase btn btn-brand btn-elevate btn-bold btn-upper"
          target="_blank"
        >
          Buy Metronic Now!
        </a>
      </div>
    </div>
    <!-- end::Demo Panel -->
  </div>
</template>

<script>
import KTOffcanvas from "@/assets/js/offcanvas.js";
import objectPath from "object-path";
import config from "@/common/config/layout.config.json";

export default {
  name: "KTStickyToolbar",
  props: {},
  components: {},
  computed: {},
  mounted() {
    new KTOffcanvas(this.$refs["kt_demo_panel"], {
      overlay: true,
      baseClass: "kt-demo-panel",
      closeBy: "kt_demo_panel_close",
      toggleBy: "kt_demo_panel_toggle"
    });
  },
  methods: {
    isActiveDemo(demo) {
      return demo === objectPath.get(config, "demo");
    }
  }
};
</script>
