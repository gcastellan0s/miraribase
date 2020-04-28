<template>
  <div class="kt-timeline-v2">
    <div class="kt-timeline-v2__items kt-padding-top-25 kt-padding-bottom-30">
      <perfect-scrollbar style="max-height: 100vh; position: relative;">
        <template v-for="(item, i) in datasrc">
          <div class="kt-timeline-v2__item" :key="`item-${i}`">
            <span class="kt-timeline-v2__item-time">{{ item.time }}</span>
            <div class="kt-timeline-v2__item-cricle">
              <i v-bind:class="item.icon"></i>
            </div>
            <div
              class="kt-timeline-v2__item-text kt-padding-top-5"
              v-bind:class="{ 'kt-timeline-v2__item-text--bold': item.bold }"
              v-html="item.text"
            ></div>
            <div
              :key="`images-${i}`"
              v-if="item.images"
              class="kt-list-pics kt-list-pics--sm kt-padding-l-20"
            >
              <template v-for="(item, i) in item.images">
                <a href="#" :key="i" v-html="item"></a>
              </template>
            </div>
          </div>
        </template>
      </perfect-scrollbar>
    </div>
  </div>
</template>

<script>
export default {
  name: "timeline-2",
  components: {},
  props: {
    datasrc: Array
  }
};
</script>
