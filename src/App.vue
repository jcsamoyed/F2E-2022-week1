<template>
  <TheNavbar />
  <router-view />
  <TheFooter />
</template>

<script>
import TheNavbar from '@/components/TheNavbar.vue';
import TheFooter from '@/components/TheFooter.vue';

export default {
  components: {
    TheNavbar,
    TheFooter,
  },
};
</script>

<style lang="scss">
@import '@/assets/scss/reset.scss';
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700&display=swap');

#app {
  font-family: 'Noto Sans TC', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow: hidden;
  * {
    font-family: 'Noto Sans TC', sans-serif;
    box-sizing: border-box;
  }
}

::-moz-selection {
  /* Code for Firefox */
  background: #754aba;
}

::selection {
  background: #754aba;
}
</style>
