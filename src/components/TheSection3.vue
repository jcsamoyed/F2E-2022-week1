<template>
  <section>
    <div class="wheel-wrapper">
      <img
        src="@/assets/images/section3/ferris-wheel.png"
        class="ferris-wheel"
        alt="年度最強合作 三大主題來襲"
      />
      <h2>
        <span data-stroke="年度最強合作">年度最強合作</span>
        <span data-stroke="三大主題來襲">三大主題來襲</span>
      </h2>
    </div>
    <img src="@/assets/images/section3/cloud-1.svg" class="cloud cloud-1" alt="雲朵" />
    <img src="@/assets/images/section3/cloud-2.svg" class="cloud cloud-2" alt="雲朵" />
    <img src="@/assets/images/section3/cloud-2.svg" class="cloud cloud-3" alt="雲朵" />
    <img src="@/assets/images/section3/cloud-1.svg" class="cloud cloud-4" alt="雲朵" />
    <img src="@/assets/images/section3/cloud-1.svg" class="cloud cloud-5" alt="雲朵" />
    <h4>
      <span data-stroke="• 各路廠商強強聯手，">• 各路廠商強強聯手，</span>
      <span data-stroke="共同設計出接地氣的網頁互動挑戰關卡 •"
        >共同設計出接地氣的網頁互動挑戰關卡 •</span
      >
    </h4>
  </section>
</template>

<script>
import { gsap } from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

export default {
  methods: {
    setAnimate() {
      const tl = gsap.timeline({
        scrollTrigger: {
          scrub: true,
          trigger: '.ferris-wheel',
          start: 'top 60%',
          end: 'top 1%',
        },
      });
      tl.from('.cloud-1', {
        xPercent: '-100',
        duration: 300,
        opacity: 0,
      })
        .from('.cloud-2', {
          xPercent: '100',
          duration: 300,
          opacity: 0,
        })
        .from('.cloud-3', {
          xPercent: '-110',
          opacity: 0,
          duration: 300,
        })
        .from('.cloud-4', {
          xPercent: '100',
          opacity: 0,
          duration: 300,
        })
        .from('.cloud-5', {
          xPercent: '-110',
          opacity: 0,
          duration: 200,
        });
    },
    h2Animate() {
      const vm = this;
      const h2 = document.querySelector('h2');
      ScrollTrigger.create({
        trigger: h2,
        markers: false,
        onEnter() {
          vm.showH2(h2);
        },
        onLeave() {
          vm.hideH2(h2);
        },
        onEnterBack() {
          vm.showH2(h2);
        },
      });
    },
    showH2(element) {
      gsap.fromTo(
        element,
        {
          opacity: 0,
          scale: 0,
          visibility: 'hidden',
        },
        {
          duration: 1,
          delay: 0.2,
          opacity: '1',
          scale: 1,
          visibility: 'visible',
          ease: 'expo',
          overwrite: 'auto',
        },
      );
    },
    hideH2(element) {
      gsap.set(element, { opacity: 0, visibility: 'hidden' });
    },
  },
  created() {
    gsap.registerPlugin(ScrollTrigger);
  },
  mounted() {
    this.setAnimate();
    this.h2Animate();
  },
};
</script>

<style lang="scss" scoped>
section {
  position: relative;
  background-color: #1a1a1a;
  padding: 80px 0;
  overflow: hidden;
}
.wheel-wrapper {
  position: relative;
}
.ferris-wheel {
  display: block;
  width: 950px;
  margin: 0 auto;
}
h2 {
  position: absolute;
  width: 100%;
  left: 50%;
  top: 53%;
  transform: translate(-50%, -50%);
  font-size: 80px;
  line-height: 97px;
  color: #f47924;
  text-align: center;
  span {
    display: block;
    &::before {
      content: attr(data-stroke);
      position: absolute;
      z-index: -1;
      -webkit-text-stroke: 10px #fff;
      text-stroke: 10px #fff;
    }
  }
}
.cloud {
  position: absolute;
}
.cloud-1 {
  width: 318px;
  left: 10%;
  top: 250px;
}
.cloud-2 {
  width: 346px;
  right: 10%;
  top: 289px;
}
.cloud-3 {
  width: 238px;
  left: 10%;
  top: 637px;
}
.cloud-4 {
  width: 385px;
  right: 15%;
  top: 700px;
}
.cloud-5 {
  width: 385px;
  left: 14%;
  top: 854px;
}
h4 {
  position: relative;
  font-weight: 700;
  font-size: 36px;
  color: #fff;
  text-align: center;
  margin-top: 80px;
  z-index: 0;
  span {
    &::before {
      content: attr(data-stroke);
      position: absolute;
      z-index: -1;
      -webkit-text-stroke: 4px #f47924;
      text-stroke: 4px #f47924;
    }
  }
}

@media screen and (max-width: 1080px) {
  h4 {
    font-size: 28px;
  }
}

@media screen and (max-width: 992px) {
  section {
    padding: 32px 0;
  }
  .ferris-wheel {
    width: 380px;
  }
  h2 {
    font-size: 33px;
    line-height: 40px;
    span {
      &::before {
        -webkit-text-stroke: 3px #fff;
        text-stroke: 3px #fff;
      }
    }
  }
  .cloud-1 {
    width: 127px;
    top: 100px;
  }
  .cloud-2 {
    width: 138px;
    top: 115px;
  }
  .cloud-3 {
    width: 95px;
    top: 254px;
  }
  .cloud-4 {
    width: 154px;
    top: 280px;
  }
  .cloud-5 {
    width: 154px;
    top: 340px;
  }
  h4 {
    font-size: 17px;
    margin-top: 32px;
  }
}

@media screen and (max-width: 640px) {
  section {
    padding: 35px 16px;
  }
  .ferris-wheel {
    width: 100%;
  }
  .cloud-1 {
    left: -8%;
  }
  .cloud-2 {
    right: -13%;
  }
  .cloud-3 {
    left: -4%;
  }
  .cloud-4 {
    right: -13%;
  }
  .cloud-5 {
    left: -13%;
  }
  h4 {
    font-size: 15px;
    line-height: 21px;
    margin-top: 60px;
    span {
      display: block;
    }
  }
}
</style>
