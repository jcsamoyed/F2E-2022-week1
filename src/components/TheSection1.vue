<template>
  <section>
    <div ref="hero" class="hero-wrapper">
      <img src="@/assets/images/section1/hero.png" alt="The F2E 4th" class="hero" />
      <div ref="ghost1" class="ghost-1"></div>
      <div ref="ghost2" class="ghost-2"></div>
      <div ref="balloon" class="balloon"></div>
    </div>
    <div class="star-wrapper"></div>
  </section>
</template>

<script>
import lottie from 'lottie-web';

export default {
  name: 'TheSection1',
  methods: {
    setAnimate() {
      lottie.loadAnimation({
        container: this.$refs.ghost1,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/ghost-1.json',
      });
      lottie.loadAnimation({
        container: this.$refs.ghost2,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/ghost-2.json',
      });
      lottie.loadAnimation({
        container: this.$refs.balloon,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/hot-air-balloon.json',
      });
    },
  },
  mounted() {
    this.setAnimate();
  },
};
</script>

<style lang="scss" scoped>
section {
  position: relative;
}
.hero-wrapper {
  position: relative;
  background-color: #000;
  padding-top: 154px;
  padding-bottom: 90px;
  height: 100%;
}
.ghost-1 {
  position: absolute;
  bottom: 20%;
  right: 20%;
  width: 200px;
}
.ghost-2 {
  position: absolute;
  bottom: 20%;
  left: 15%;
  width: 200px;
}
.balloon {
  position: absolute;
  top: 15%;
  left: 20%;
  width: 200px;
}
.hero {
  display: block;
  width: 100%;
  max-width: 1032px;
  margin: 0 auto;
}
.star-wrapper {
  position: absolute;
  bottom: 0;
  left: 0;
  transform: translateY(50%);
  width: 100%;
  height: 5vw;
  background-image: url('@/assets/images/section1/star.svg');
  background-size: contain;
  background-repeat: repeat-x;
  z-index: 2;
}
@media screen and (max-width: 768px) {
  section {
    height: 90vh;
  }
  .star-wrapper {
    height: 9vw;
  }
}
</style>
