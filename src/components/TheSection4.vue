<template>
  <section>
    <div class="week-wrapper">
      <div class="week-page page1">
        <img src="@/assets/images/section4/wheel-1.png" class="wheel" alt="Week1" />
        <div class="content">
          <h3 class="week1" data-stroke="Week1">Week1</h3>
          <p>
            The F2E 活動網站設計<br />
            標籤：視差滾動 <br />
            贊助商：版塊設計
          </p>
          <a
            href="https://2022.thef2e.com/news/week1"
            target="_blank"
            rel="noreferrer noopener"
            title="查看關卡細節"
            class="primary orange"
            >查看關卡細節</a
          >
        </div>
      </div>
      <div class="week-page page2">
        <img src="@/assets/images/section4/wheel-2.png" class="wheel" alt="Week2" />
        <div class="content">
          <h3 class="week2" data-stroke="Week2">Week2</h3>
          <p>
            今晚，我想來點點簽<br />
            標籤：Canvas<br />
            贊助商：凱鈿行動科技
          </p>
          <a
            href="https://2022.thef2e.com/news/week2"
            target="_blank"
            rel="noreferrer noopener"
            title="查看關卡細節"
            class="primary purple"
            >查看關卡細節</a
          >
        </div>
      </div>
      <div class="week-page page3">
        <img src="@/assets/images/section4/wheel-3.png" class="wheel" alt="Week3" />
        <div class="content">
          <h3 class="week3" data-stroke="Week3">Week3</h3>
          <p>
            Scrum 新手村<br />
            標籤：JS draggable<br />
            贊助商：鈦坦科技
          </p>
          <a
            href="https://2022.thef2e.com/news/week3"
            target="_blank"
            rel="noreferrer noopener"
            title="查看關卡細節"
            class="primary yellow"
            >查看關卡細節</a
          >
        </div>
      </div>
      <img src="@/assets/images/section4/cloud.png" class="cloud" alt="雲朵" />
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
          trigger: '.week-wrapper',
          scrub: true,
          pin: true,
          markers: false,
          start: 'top 10%',
        },
      });
      tl.to('.page1', { xPercent: '-100', opacity: 0 });
      tl.to('.page2', { xPercent: '-100', opacity: 0 });
      tl.to('.page3', { xPercent: '-100', opacity: 0 });
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
  background-color: #1a1a1a;
}
.week-wrapper {
  position: relative;
  display: flex;
  width: 100%;
  height: 90vh;
  margin: 0 auto;
  overflow: hidden;
}
.week-page {
  position: absolute;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  width: 100%;
  height: 100%;
  background-color: #1a1a1a;
  &.page1 {
    z-index: 3;
  }
  &.page2 {
    z-index: 2;
  }
  &.page3 {
    z-index: 1;
  }
}
.wheel {
  width: 45%;
}
.content {
  color: #fff;
  line-height: 1.5;
  margin-left: 20px;
  margin-bottom: 40px;
}
h3 {
  position: relative;
  font-size: 60px;
  font-weight: 700;
  text-align: center;
  z-index: 0;
  margin-bottom: 20px;
  &::before {
    content: attr(data-stroke);
    position: absolute;
    z-index: -1;
  }
  &.week1 {
    color: #f47924;
    &::before {
      -webkit-text-stroke: 5px #fff;
      text-stroke: 5px #fff;
    }
  }
  &.week2 {
    color: #754aba;
    &::before {
      -webkit-text-stroke: 5px #f47924;
      text-stroke: 5px #f47924;
    }
  }
  &.week3 {
    color: #f9b233;
    &::before {
      -webkit-text-stroke: 5px #754aba;
      text-stroke: 5px #754aba;
    }
  }
}
p {
  font-size: 36px;
  font-weight: 700;
  text-align: center;
  margin-bottom: 80px;
}
.primary {
  display: block;
  width: 340px;
  font-size: 36px;
  font-weight: 700;
  text-align: center;
  text-decoration: none;
  padding: 16px 18px;
  margin: 0 auto;
  color: #fff;
  border: none;
  border-radius: 64px;
  cursor: pointer;
  transition-duration: 0.2s;
  &.orange {
    background-color: #f47924;
    &:hover {
      background-color: #fea669;
    }
    &:active {
      background-color: #be5106;
    }
  }
  &.yellow {
    background-color: #f9b233;
    &:hover {
      background-color: #ffd384;
    }
    &:active {
      background-color: #e19000;
    }
  }
  &.purple {
    background-color: #754aba;
    &:hover {
      background-color: #b287f8;
    }
    &:active {
      background-color: #4b2e7a;
    }
  }
}
.cloud {
  position: absolute;
  width: 100%;
  height: fit-content;
  z-index: 5;
  bottom: -22vw;
}

@media screen and (max-width: 1680px) {
  .cloud {
    bottom: -16vw;
  }
}

@media screen and (max-width: 1280px) {
  .wheel {
    width: 40%;
    min-width: 300px;
  }
  .content {
    margin-bottom: 5%;
  }
  h3 {
    font-size: 24px;
  }
  p {
    font-size: 17px;
    margin-bottom: 20px;
  }
  .primary {
    width: 153px;
    font-size: 17px;
    padding: 8px 15px;
  }
  .cloud {
    bottom: -6vw;
  }
}

@media screen and (max-width: 1080px) {
  .cloud {
    bottom: 0;
  }
}

@media screen and (max-width: 992px) {
  .cloud {
    bottom: 5vw;
  }
}

@media screen and (max-width: 768px) {
  .cloud {
    bottom: 18vw;
  }
}

@media screen and (max-width: 640px) {
  .week-wrapper {
    height: 100vh;
  }
  .week-page {
    flex-direction: column-reverse;
  }
  .content {
    margin-left: 0;
    margin-top: 56px;
    margin-bottom: 60px;
  }
  .cloud {
    bottom: 8vh;
  }
}
</style>
