<template>
  <div class="kt-grid kt-grid--ver kt-grid--root">
    <div
      class="kt-grid__item kt-grid__item--fluid kt-grid kt-error-v2"
      :style="{
        backgroundImage: `url(${backgroundImage})`
      }"
    >
      <div class="kt-error_container">
        <span class="kt-error_title2 kt-font-light">
          <h1>OOPS!</h1>
        </span>
        <span class="kt-error_desc kt-font-light">
          Something went wrong here
        </span>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/sass/pages/error/error-2.scss";
</style>

<script>
export default {
  name: "Error-2",
  mounted() {},
  computed: {
    backgroundImage() {
      return process.env.BASE_URL + "assets/media/error/bg2.jpg";
    }
  }
};
</script>
