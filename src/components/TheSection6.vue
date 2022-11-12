<template>
  <section id="section6">
    <div class="container">
      <h4>• 區區修練已經無法滿足了嗎? 還有比賽等著你! •</h4>
      <h3 data-stroke="評審機制">評審機制</h3>
      <div class="grave-wrapper">
        <img src="@/assets/images/section6/grave-1.svg" class="grave-1" alt="方形墳墓" />
        <img src="@/assets/images/section6/grave-2.svg" class="grave-2" alt="圓形墳墓" />
        <img src="@/assets/images/section6/grave-3.svg" class="grave-3" alt="十字架墳墓" />
      </div>
    </div>
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
          trigger: '.grave-wrapper',
          markers: false,
          start: 'top 50%',
          end: 'top 1%',
        },
      });
      tl.from('.grave-1', {
        opacity: 0,
        yPercent: 3,
        duration: 0.8,
      })
        .from('.grave-2', {
          opacity: 0,
          yPercent: 3,
          duration: 0.8,
        })
        .from('.grave-3', {
          opacity: 0,
          yPercent: 3,
          duration: 0.8,
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
  background-color: #f47924;
  background-image: url(@/assets/images/section6/ghost.svg);
  background-position: center right 20%;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: 50vh;
}
.container {
  width: 90%;
  max-width: 1300px;
  padding: 110px 0;
  margin: 0 auto;
}
h4 {
  font-size: 36px;
  font-weight: 700;
  text-align: center;
  margin-bottom: 50px;
}
h3 {
  position: relative;
  font-size: 60px;
  font-weight: 700;
  text-align: center;
  color: #754aba;
  z-index: 0;
  margin-bottom: 96px;
  &::before {
    content: attr(data-stroke);
    position: absolute;
    z-index: -1;
    -webkit-text-stroke: 5px #fff;
    text-stroke: 5px #fff;
  }
}
.grave-wrapper {
  width: 50%;
  z-index: 1;
  .grave-1 {
    width: 718px;
  }
  .grave-2 {
    width: 660px;
    margin-left: 298px;
    margin-top: -190px;
  }
  .grave-3 {
    width: 869px;
    margin-top: -378px;
  }
}
.ghost-wrapper {
  width: 50%;
  margin-top: 100px;
  margin-left: 110px;
  img {
    display: block;
  }
}

@media screen and (max-width: 1280px) {
  .grave-wrapper {
    width: 100%;
    .grave-1 {
      width: 60%;
    }
    .grave-2 {
      width: 55%;
    }
    .grave-3 {
      width: 70%;
      margin-top: -240px;
    }
  }
}

@media screen and (max-width: 1080px) {
  .container {
    padding: 44px 0;
  }
  h4 {
    font-size: 17px;
    margin-bottom: 16px;
  }
  h3 {
    font-size: 24px;
    margin-bottom: 40px;
  }
}

@media screen and (max-width: 768px) {
}

@media screen and (max-width: 640px) {
  section {
    background-attachment: scroll;
  }
  .container {
    width: 95%;
  }
  h4 {
    font-size: 15px;
    line-height: 1.2;
  }
  .grave-wrapper {
    .grave-1 {
      width: 80%;
    }
    .grave-2 {
      width: 75%;
      margin-left: 25%;
      margin-top: -15%;
    }
    .grave-3 {
      width: 90%;
      margin-top: -35%;
    }
  }
}
</style>
