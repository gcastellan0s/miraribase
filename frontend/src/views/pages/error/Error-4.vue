<template>
  <div class="kt-grid kt-grid--ver kt-grid--root">
    <div
      class="kt-grid__item kt-grid__item--fluid kt-grid kt-error-v4"
      :style="{
        backgroundImage: `url(${backgroundImage})`
      }"
    >
      <div class="kt-error_container">
        <h1 class="kt-error_number">
          404
        </h1>
        <p class="kt-error_title">
          ERROR
        </p>
        <p class="kt-error_description">
          Nothing left to do here.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/assets/sass/pages/error/error-4.scss";
</style>

<script>
export default {
  name: "Error-4",
  mounted() {},
  computed: {
    backgroundImage() {
      return process.env.BASE_URL + "assets/media/error/bg4.jpg";
    }
  }
};
</script>
