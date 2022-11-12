<template>
  <section id="section1">
    <div class="hero-wrapper">
      <div ref="cloudAnimate" class="cloud-animate"></div>
      <div ref="cloudAnimateM" class="cloud-animate-m"></div>
      <div ref="cloudBg" class="cloud-bg"></div>
      <div ref="cloudBgM" class="cloud-bg-m"></div>
      <div ref="playground" class="playground"></div>
      <div ref="playgroundM" class="playground-m"></div>
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
        container: this.$refs.playgroundM,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/playground-m.json',
      });
      lottie.loadAnimation({
        container: this.$refs.cloudAnimate,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/cloud.json',
      });
      lottie.loadAnimation({
        container: this.$refs.cloudAnimateM,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/cloud-m.json',
      });
      lottie.loadAnimation({
        container: this.$refs.cloudBg,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/cloud-bg.json',
      });
      lottie.loadAnimation({
        container: this.$refs.cloudBgM,
        renderer: 'svg',
        loop: true,
        autoplay: true,
        path: 'lottie/cloud-bg-m.json',
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
  padding-bottom: 3%;
}
.cloud-animate {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1;
}
.cloud-animate-m {
  display: none;
}
.cloud-bg {
  position: absolute;
  top: 5%;
  left: 0;
  width: 100%;
}
.cloud-bg-m {
  display: none;
}
.playground {
  width: 100%;
  max-width: 900px;
  margin: 0 auto;
}
.playground-m {
  display: none;
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
  .cloud-animate {
    top: 10%;
  }
  .cloud-bg {
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
  .cloud-animate {
    top: 25%;
  }
  .cloud-bg {
    top: 25%;
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
  .balloon {
    top: 15%;
    width: 150px;
  }
  .star-wrapper {
    height: 9vw;
  }
}

@media screen and (max-width: 640px) {
  section {
    height: initial;
    background-color: #000;
    padding: 0;
  }
  .cloud-animate {
    display: none;
  }
  .cloud-animate-m {
    display: block;
    position: absolute;
    top: 10%;
    left: 0;
    width: 100%;
    z-index: 1;
  }
  .cloud-bg {
    display: none;
  }
  .cloud-bg-m {
    display: block;
    position: absolute;
    top: 15%;
    left: 0;
    width: 100%;
  }
  .playground {
    display: none;
  }
  .playground-m {
    display: block;
    width: 100%;
    transform: scale(105%);
  }
  .hero-wrapper {
    min-height: initial;
  }
  .ghost-1 {
    right: 0;
    width: 100px;
  }
  .ghost-2 {
    left: 0;
    width: 100px;
  }
  .balloon {
    left: initial;
    right: 0;
    width: 100px;
  }
}
</style>
