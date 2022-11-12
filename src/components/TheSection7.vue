<template>
  <section id="section7">
    <div class="container">
      <img src="@/assets/images/section7/pumpkin.svg" class="pumpkin pumpkin-left" alt="南瓜" />
      <h3 data-stroke="贊助單位">贊助單位</h3>
      <img src="@/assets/images/section7/pumpkin.svg" class="pumpkin pumpkin-right" alt="南瓜" />
      <div class="sponsor-wrapper">
        <a href="https://blockstudio.tw/" target="_blank" rel="noreferrer noopener" class="sponsor">
          <img src="@/assets/images/section7/logo-blockstudio.png" alt="版塊 Block Studio logo" />
        </a>
        <a
          href="https://titansoft.com/tw"
          target="_blank"
          rel="noreferrer noopener"
          class="sponsor"
        >
          <img src="@/assets/images/section7/logo-titan.png" alt="新加坡商鈦坦科技 logo" />
        </a>
        <a
          href="https://www.kdanmobile.com/zh-tw"
          target="_blank"
          rel="noreferrer noopener"
          class="sponsor"
        >
          <img src="@/assets/images/section7/logo-kdan.png" alt="凱鈿行動科技 logo" />
        </a>
      </div>
      <p class="note">The F2E 官方備註：LOGO 僅授權為挑戰者設計本活動投稿用。</p>
    </div>
  </section>
</template>

<style lang="scss" scoped>
section {
  position: relative;
  background-color: #1a1a1a;
  background-image: url(@/assets/images/section7/background.png);
  background-size: contain;
  background-position: bottom center;
  background-attachment: fixed;
  background-repeat: no-repeat;
}
.container {
  width: 80%;
  max-width: 1300px;
  padding: 200px 0;
  margin: 0 auto;
}
h3 {
  position: relative;
  font-size: 60px;
  font-weight: 700;
  text-align: center;
  color: #f47924;
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
.pumpkin {
  position: absolute;
  width: 160px;
  top: 113px;
  &.pumpkin-left {
    left: 5%;
    transform: rotate(-20deg);
  }
  &.pumpkin-right {
    right: 5%;
    transform: rotate(20deg);
  }
}
.sponsor-wrapper {
  display: flex;
  justify-content: center;
  column-gap: 80px;
}
.sponsor {
  padding: 20px;
  background-color: #fff;
  border-radius: 20px;
  transition-duration: 0.3s;
  cursor: pointer;
  &:hover {
    background-color: #f47924;
  }
  img {
    width: 100%;
    border-radius: 20px;
  }
}
.note {
  color: #fff;
  font-size: 25px;
  text-align: center;
  margin-top: 60px;
}

@media screen and (max-width: 1080px) {
  .container {
    padding: 80px 0;
  }
  .pumpkin {
    width: 90px;
    top: 32px;
  }
  h3 {
    font-size: 24px;
    margin-bottom: 40px;
  }
  .sponsor-wrapper {
    column-gap: 20px;
  }
  .note {
    font-size: 14px;
    margin-top: 24px;
  }
}

@media screen and (max-width: 640px) {
  section {
    background-size: 180%;
    background-position: center center;
  }
  .pumpkin {
    width: 72px;
  }
  .container {
    width: 90%;
    padding: 50px 0;
  }
  .sponsor-wrapper {
    flex-direction: column;
    align-items: center;
    row-gap: 20px;
  }
  .sponsor {
    width: 60%;
    padding: 8px;
  }
  .note {
    font-size: 12px;
    margin-top: 16px;
  }
}
</style>
