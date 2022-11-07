<template>
  <section>
    <div class="hero-wrapper">
      <div ref="cloud" class="cloud"></div>
      <div ref="playground" class="playground"></div>
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
        container: this.$refs.playground,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/playground.json',
      });
      lottie.loadAnimation({
        container: this.$refs.cloud,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/cloud.json',
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
  display: flex;
  align-items: center;
  position: relative;
  background-color: #000;
  min-height: 90vh;
  padding-top: 80px;
}
.cloud {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
}
.playground {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
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

@media screen and (max-width: 1280px) {
  .cloud {
    top: 10%;
  }
  .ghost-1 {
    right: 10%;
  }
  .ghost-2 {
    left: 5%;
  }
  .balloon {
    left: 10%;
  }
}

@media screen and (max-width: 992px) {
  .cloud {
    top: 20%;
  }
  .ghost-1 {
    bottom: 30%;
    width: 150px;
  }
  .ghost-2 {
    bottom: 30%;
    width: 150px;
  }
  .balloon {
    top: 10%;
    width: 150px;
  }
}

@media screen and (max-width: 768px) {
  section {
    height: 90vh;
  }
  .cloud {
    top: 25%;
  }
  .star-wrapper {
    height: 9vw;
  }
}

@media screen and (max-width: 640px) {
  section {
    height: initial;
    background-color: #000;
    padding: 20% 0;
  }
  .hero-wrapper {
    min-height: initial;
  }
  .playground {
    transform: scale(110%);
  }
  .cloud {
    top: 25%;
  }
}
</style>
