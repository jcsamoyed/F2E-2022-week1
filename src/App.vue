<template>
  <TheNavbar />
  <router-view />
</template>

<script>
import TheNavbar from '@/components/TheNavbar.vue';

export default {
  components: {
    TheNavbar,
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
</style>
