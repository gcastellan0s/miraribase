<template>
  <div class="kt-widget4">
    <perfect-scrollbar style="max-height: 100vh; position: relative;">
      <template v-for="(item, i) in datasrc">
        <div class="kt-widget4__item" :key="`item-${i}`">
          <div class="kt-widget4__pic kt-widget4__pic--pic">
            <img :src="item.image" alt="" />
          </div>
          <div class="kt-widget4__info">
            <a href="#" class="kt-widget4__username">{{ item.username }}</a>
            <p class="kt-widget4__text">{{ item.text }}</p>
          </div>
          <a href="#" class="btn" v-bind:class="item.button.style">{{
            item.button.text
          }}</a>
        </div>
      </template>
    </perfect-scrollbar>
  </div>
</template>

<script>
export default {
  name: "widget-4",
  components: {},
  props: {
    datasrc: Array
  }
};
</script>
