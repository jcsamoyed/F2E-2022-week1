<template>
  <nav>
    <div class="logo">
      <router-link to="/"><img src="@/assets/images/logo.svg" alt="The F2E" /></router-link>
    </div>
    <button @click="toggleHamburger" class="hamburger">
      <div class="line top"></div>
      <div class="line middle"></div>
      <div class="line bottom"></div>
    </button>
    <ul :class="{ open: isShowMenu }">
      <li>
        <router-link to="/" @click="handleScroll('2', 'end')">活動目的</router-link>
      </li>
      <li>
        <router-link to="/" @click="handleScroll('3', 'start')">關卡資訊</router-link>
      </li>
      <li>
        <router-link to="/" @click="handleScroll('5', 'start')">活動說明</router-link>
      </li>
      <li>
        <router-link to="/" @click="handleScroll('6', 'start')">獎項</router-link>
      </li>
      <li>
        <router-link to="/" @click="handleScroll('7', 'start')">贊助單位</router-link>
      </li>
      <li class="btn-wrapper">
        <button @click="shareLink" class="primary yellow">立即分享</button>
        <button @click="goSignUp" class="primary purple">註冊報名</button>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'TheNavbar',
  data() {
    return {
      url: window.location.href,
      isShowMenu: false,
    };
  },
  methods: {
    handleScroll(id, block) {
      document
        .getElementById(`section${id}`)
        .scrollIntoView({ behavior: 'smooth', block, inline: 'nearest' });
    },
    toggleHamburger() {
      this.isShowMenu = !this.isShowMenu;
    },
    async shareLink() {
      await navigator.share({
        title: 'The F2E 前端 & UI 修煉精神時光屋 :: 一朵空氣',
        url: this.url,
      });
    },
    goSignUp() {
      window.open('https://2022.thef2e.com/');
    },
  },
};
</script>

<style lang="scss" scoped>
nav {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 10;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 80px;
  background-color: #de611e;
}
.logo {
  width: 165px;
  img {
    width: 100%;
  }
}
.hamburger {
  display: none;
  flex-direction: column;
  row-gap: 8px;
  padding: 0;
  background-color: transparent;
  border: none;
  cursor: pointer;
  .line {
    width: 30px;
    height: 1px;
    background-color: #fff;
  }
}
ul {
  display: flex;
  align-items: center;
  column-gap: 30px;
  a {
    color: #fff;
    font-size: 16px;
    text-decoration: none;
    transition-duration: 0.2s;
    &:hover {
      opacity: 0.8;
    }
  }
}
.btn-wrapper {
  display: flex;
  align-items: center;
  column-gap: 20px;
}
.primary {
  width: 120px;
  font-size: 16px;
  text-align: center;
  padding: 8px 15px;
  color: #fff;
  border: none;
  border-radius: 64px;
  cursor: pointer;
  transition-duration: 0.2s;
  &.yellow {
    display: none;
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

@media screen and (max-width: 1080px) {
  nav {
    padding: 12px 35px;
  }
}

@media screen and (max-width: 992px) {
  nav {
    flex-wrap: wrap;
    padding: 20px 16px;
  }
  .logo {
    width: 115px;
  }
  .hamburger {
    display: flex;
  }
  ul {
    display: none;
    width: 100%;
    padding: 0 20px;
    li {
      width: 100%;
      text-align: center;
      border-bottom: solid 1px #754aba;
      a {
        display: block;
        font-size: 15px;
        padding: 16px;
      }
      &.btn-wrapper {
        flex-direction: column;
        justify-content: center;
        border-bottom: none;
        padding: 0;
      }
    }
    &.open {
      display: flex;
      flex-wrap: wrap;
    }
  }
  .primary {
    margin-top: 20px;
  }
}

@media screen and (max-width: 768px) {
  .primary {
    &.yellow {
      display: block;
    }
  }
}
</style>
