<template>
  <section>
    <img src="@/assets/images/section2/lollipop.png" alt="棒棒糖" class="lollipop left" />
    <div class="booth-wrapper">
      <img
        src="@/assets/images/section2/ticket-booth-1.png"
        alt="一朵空氣售票亭上半部"
        class="booth booth-1"
      />
      <img src="@/assets/images/section2/coupon.svg" alt="優惠券" class="coupon" />
      <img
        src="@/assets/images/section2/ticket-booth-2.png"
        alt="一朵空氣售票亭下半部"
        class="booth booth-2"
      />
      <p class="p1">你是否也有以下困擾？</p>
      <p class="p2">羨慕別人的酷酷網頁動畫？</p>
      <p class="p3">滿足不了同事的許願？</p>
      <p class="p4">動畫技能樹太雜無從下手？</p>
      <p class="p5">讓我來幫你！</p>
    </div>
    <img src="@/assets/images/section2/lollipop.png" alt="棒棒糖" class="lollipop right" />
  </section>
  <div class="coupon-wrapper">
    <img src="@/assets/images/section2/coupon-huge.svg" alt="優惠券" class="coupon-huge" />
  </div>
</template>

<script>
import { gsap } from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

export default {
  methods: {
    setAnimate() {
      const tl = gsap.timeline({
        scrollTrigger: {
          trigger: '.booth-wrapper',
          markers: false,
          start: 'top 20%',
          end: 'top 1%',
        },
      });
      tl.to('.lollipop', {
        yPercent: '30',
        ease: 'none',
        duration: 3,
        repeat: -1,
      })
        .from(
          '.p1',
          {
            scale: 0,
            ease: 'expo',
            duration: 1,
          },
          '<',
        )
        .from('.p2', {
          scale: 0,
          ease: 'expo',
          duration: 1,
        })
        .from('.p3', {
          scale: 0,
          ease: 'expo',
          duration: 1,
        })
        .from('.p4', {
          scale: 0,
          ease: 'expo',
          duration: 1,
        })
        .from('.p5', {
          scale: 0,
          ease: 'expo',
          duration: 1,
        })
        .to('.coupon', {
          yPercent: 40,
          ease: 'expo',
          duration: 1,
        })
        .to('.coupon-huge', {
          xPercent: 400,
          ease: 'expo',
          duration: 10,
        });
    },
  },
  created() {
    gsap.registerPlugin(ScrollTrigger);
  },
  mounted() {
    this.setAnimate();
  },
};
</script>

<style lang="scss" scoped>
section {
  position: relative;
  background-color: #532d83;
  overflow: hidden;
}
.booth-wrapper {
  position: relative;
  font-size: 0;
  height: 90vh;
  z-index: 5;
}
.booth {
  display: block;
  width: 878px;
  margin: 0 auto;
  &.booth-1 {
    position: absolute;
    left: 50%;
    bottom: 40%;
    transform: translateX(-50%);
    z-index: 3;
  }
  &.booth-2 {
    position: absolute;
    left: 50%;
    bottom: 17%;
    transform: translateX(-50%);
    z-index: 1;
  }
}
.coupon {
  position: absolute;
  left: 50%;
  bottom: 30%;
  transform: translateX(-50%);
  width: 150px;
  z-index: 2;
}
.lollipop {
  position: absolute;
  width: 10%;
  top: -50%;
  &.left {
    left: 10%;
  }
  &.right {
    right: 10%;
  }
}
.coupon-wrapper {
  position: relative;
}
.coupon-huge {
  position: absolute;
  z-index: 5;
  height: 70vh;
  transform: translate(-100%, -90%);
}
p {
  position: absolute;
  width: 20%;
  top: 20%;
  right: 16%;
  padding: 30px;
  font-size: 36px;
  font-weight: 700;
  line-height: 1.2;
  color: #1a1a1a;
  background-color: #fff;
  border-radius: 36px;
  z-index: 3;
}
.p5 {
  width: initial;
  top: 40%;
  right: initial;
  left: 15%;
}

@media screen and (max-width: 1280px) {
  p {
    font-size: 26px;
  }
}

@media screen and (max-width: 992px) {
  .booth-wrapper {
    height: 70vh;
  }
  .booth {
    width: 650px;
    &.booth-2 {
      bottom: 18%;
    }
  }
  p {
    font-size: 20px;
  }
}

@media screen and (max-width: 768px) {
  .booth-wrapper {
    height: 60vh;
  }
  .booth {
    width: 480px;
    &.booth-2 {
      bottom: 23%;
    }
  }
  .coupon {
    width: 100px;
  }
  .coupon-huge {
    height: 50vh;
  }
  p {
    padding: 20px;
    width: 50%;
  }
}

@media screen and (max-width: 640px) {
  .booth-wrapper {
    height: 50vh;
  }
  .booth {
    width: 330px;
    &.booth-2 {
      bottom: 24%;
    }
  }
  .coupon {
    width: 60px;
  }
  p {
    font-size: 16px;
    padding: 16px;
  }
}
</style>
