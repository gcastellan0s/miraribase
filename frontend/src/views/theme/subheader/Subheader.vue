<template>
  <div class="kt-subheader kt-grid__item" id="kt_subheader">
    <div
      class="kt-container"
      v-bind:class="{ 'kt-container--fluid': widthFluid }"
    >
      <div class="kt-subheader__main">
        <h3 class="kt-subheader__title">
          {{ title }}
        </h3>
        <div class="kt-subheader__breadcrumbs">
          <router-link :to="'/'" class="kt-subheader__breadcrumbs-home"
            ><i class="flaticon2-shelter"></i
          ></router-link>

          <template v-for="(breadcrumb, i) in breadcrumbs">
            <span
              :key="`${i}-${breadcrumb.id}`"
              class="kt-subheader__breadcrumbs-separator"
            ></span>
            <router-link
              v-if="breadcrumb.route"
              :key="i"
              :to="breadcrumb.route"
              class="kt-subheader__breadcrumbs-link"
            >
              {{ breadcrumb.title }}
            </router-link>
            <span
              class="kt-subheader__desc"
              :key="i"
              v-if="!breadcrumb.route"
              >{{ breadcrumb.title }}</span
            >
          </template>
        </div>
      </div>
      <div class="kt-subheader__toolbar">
        <div class="kt-subheader__wrapper">
          <a href="#" class="btn kt-subheader__btn-primary">
            Actions &nbsp;
            <!--<i class="flaticon2-calendar-1"></i>-->
          </a>

          <div
            class="dropdown dropdown-inline"
            v-b-tooltip.hover.left="'Quick actions'"
          >
            <a
              href="#"
              class="btn btn-icon"
              data-toggle="dropdown"
              aria-haspopup="true"
              aria-expanded="false"
            >
              <img
                svg-inline
                class="kt-svg-icon kt-svg-icon--success kt-svg-icon--md"
                src="@/assets/media/icons/svg/Files/File-plus.svg"
                alt=""
              />
              <!--<i class="flaticon2-plus"></i>-->
            </a>
            <div
              class="dropdown-menu dropdown-menu-fit dropdown-menu-md dropdown-menu-right"
            >
              <!--begin::Nav-->
              <ul class="kt-nav">
                <li class="kt-nav__head">
                  Add anything or jump to:
                  <i
                    class="flaticon2-information"
                    v-b-tooltip.hover.bottom="'Click to learn more...'"
                  ></i>
                </li>
                <li class="kt-nav__separator"></li>
                <li class="kt-nav__item">
                  <a href="#" class="kt-nav__link">
                    <i class="kt-nav__link-icon flaticon2-drop"></i>
                    <span class="kt-nav__link-text">Order</span>
                  </a>
                </li>
                <li class="kt-nav__item">
                  <a href="#" class="kt-nav__link">
                    <i class="kt-nav__link-icon flaticon2-calendar-8"></i>
                    <span class="kt-nav__link-text">Ticket</span>
                  </a>
                </li>
                <li class="kt-nav__item">
                  <a href="#" class="kt-nav__link">
                    <i class="kt-nav__link-icon flaticon2-telegram-logo"></i>
                    <span class="kt-nav__link-text">Goal</span>
                  </a>
                </li>
                <li class="kt-nav__item">
                  <a href="#" class="kt-nav__link">
                    <i class="kt-nav__link-icon flaticon2-new-email"></i>
                    <span class="kt-nav__link-text">Support Case</span>
                    <span class="kt-nav__link-badge">
                      <span class="kt-badge kt-badge--success">5</span>
                    </span>
                  </a>
                </li>
                <li class="kt-nav__separator"></li>
                <li class="kt-nav__foot">
                  <a class="btn btn-label-brand btn-bold btn-sm" href="#"
                    >Upgrade plan</a
                  >
                  <a
                    class="btn btn-clean btn-bold btn-sm"
                    href="#"
                    v-b-tooltip.hover.bottom="'Click to learn more...'"
                    >Learn more</a
                  >
                </li>
              </ul>
              <!--end::Nav-->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "KTSubheader",
  props: {
    breadcrumbs: Array,
    title: String
  },
  computed: {
    ...mapGetters(["layoutConfig"]),

    /**
     * Check if subheader width is fluid
     */
    widthFluid() {
      return this.layoutConfig("subheader.width") === "fluid";
    }
  }
};
</script>
