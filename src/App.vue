<template>
  <div id="app">
    <v-header />
    <v-game />
    <v-rules />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { mapActions } from "vuex";

@Component({
  components: {
    VHeader: () => import("@/components/VHeader.vue"),
    VGame: () => import("@/components/VGame.vue"),
    VRules: () => import("@/components/VRules.vue")
  },
  created() {
    this.$store.dispatch('loadBonus')
    this.$store.dispatch('loadScore')
  }
})
export default class App extends Vue {}
</script>

<style lang="scss" scoped>
#app {
  margin: 0 auto;
  padding: mobile-vw(30px);

  @include desktop {
    padding: desktop-vw(46px) 0;
    max-width: desktop-vw(700px);
  }
}
</style>
