<template>
  <nav>
    <div class="logo">
      <router-link to="/"><img src="@/assets/images/logo.svg" alt="The F2E" /></router-link>
    </div>
    <ul>
      <li>
        <router-link to="/">活動目的</router-link>
      </li>
      <li>
        <router-link to="/">關卡資訊</router-link>
      </li>
      <li>
        <router-link to="/">活動說明</router-link>
      </li>
      <li>
        <router-link to="/">獎項</router-link>
      </li>
      <li>
        <router-link to="/">贊助單位</router-link>
      </li>
      <li><BaseButton>註冊報名</BaseButton></li>
    </ul>
  </nav>
</template>

<script>
import BaseButton from '@/components/BaseButton.vue';

export default {
  name: 'TheNavbar',
  components: {
    BaseButton,
  },
};
</script>

<style lang="scss" scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30px 50px;
}
ul {
  display: flex;
  align-items: center;
  column-gap: 50px;
  a {
    color: #fff;
    font-size: 25px;
    text-decoration: none;
  }
}
</style>
