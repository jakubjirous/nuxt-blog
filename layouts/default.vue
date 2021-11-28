<template>
  <div>
    <TheHeader @sidenavToggle="onToggleSideNav"/>
    <TheSidenav :show="displaySideNav" @close="onCloseSideNav"/>
    <nuxt/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import TheHeader from '~/components/Navigation/TheHeader.vue';
import TheSidenav from '~/components/Navigation/TheSidenav.vue';

export default Vue.extend({
  components: {
    TheHeader,
    TheSidenav,
  },
  data() {
    return {
      displaySideNav: false
    };
  },
  methods: {
    onToggleSideNav() {
      this.displaySideNav = !this.displaySideNav;
    },
    onCloseSideNav() {
      this.displaySideNav = false;
    }
  }
});
</script>

<style>
html {
  font-family: 'Roboto', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
}

body {
  margin: 0;
}

h1, h2, h3 {
  font-family: 'Rock Salt', cursive;
}
</style>
