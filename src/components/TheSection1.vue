<template>
  <section>
    <div class="hero-wrapper">
      <img src="@/assets/images/section1/hero.png" alt="The F2E 4th" class="hero" />
    </div>
    <div class="star-wrapper"></div>
  </section>
</template>

<script>
export default {
  name: 'TheSection1',
};
</script>

<style lang="scss" scoped>
section {
  position: relative;
}
.hero-wrapper {
  background-color: #000;
  padding-top: 154px;
  padding-bottom: 90px;
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
}
@media screen and (max-width: 768px) {
  .star-wrapper {
    height: 9vw;
  }
}
</style>
