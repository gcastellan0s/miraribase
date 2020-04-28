<template>
  <v-app>
    <transition name="fade-in-up">
      <router-view></router-view>
    </transition>
  </v-app>
</template>

<style lang="scss" scoped>
.theme--light.v-application {
  background: inherit;
}
</style>

<script>
export default {
  components: {}
};
</script>
