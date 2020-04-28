<template>
  <div class="kt-grid kt-grid--ver kt-grid--root">
    <div
      class="kt-grid__item kt-grid__item--fluid kt-grid kt-error-v6"
      :style="{
        backgroundImage: `url(${backgroundImage})`
      }"
    >
      <div class="kt-error_container">
        <div class="kt-error_subtitle kt-font-light">
          <h1>Oops...</h1>
        </div>
        <p class="kt-error_description kt-font-light">
          Looks like something went wrong.<br />
          We're working on it
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/sass/pages/error/error-6.scss";
</style>

<script>
export default {
  name: "Error-6",
  mounted() {},
  computed: {
    backgroundImage() {
      return process.env.BASE_URL + "assets/media/error/bg6.jpg";
    }
  }
};
</script>
