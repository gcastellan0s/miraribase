<template>
  <div class="kt-widget5">
    <perfect-scrollbar style="max-height: 100vh; position: relative;">
      <template v-for="(item, i) in datasrc">
        <div class="kt-widget5__item" :key="`item-${i}`">
          <div class="kt-widget5__content">
            <div class="kt-widget5__pic">
              <img class="kt-widget7__img" :src="item.image" alt="" />
            </div>
            <div class="kt-widget5__section">
              <a href="#" class="kt-widget5__title">
                {{ item.title }}
              </a>
              <p class="kt-widget5__desc">
                {{ item.text }}
              </p>
              <div class="kt-widget5__info" v-html="item.info"></div>
            </div>
          </div>
          <div class="kt-widget5__content" v-html="item.stats"></div>
        </div>
      </template>
    </perfect-scrollbar>
  </div>
</template>

<script>
export default {
  name: "widget-5",
  components: {},
  props: {
    datasrc: Array
  }
};
</script>
