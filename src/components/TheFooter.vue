<template>
  <footer>
    <p>Copyright © 2022 HexSchool.All rights reserved.</p>
  </footer>
</template>

<style lang="scss" scoped>
footer {
  background: #de611e;
  padding: 34px;
}
p {
  color: #fff;
  font-size: 16px;
  text-align: center;
}

@media screen and (max-width: 768px) {
  footer {
    padding: 10px;
  }
  p {
    font-size: 12px;
  }
}

@media screen and (max-width: 640px) {
  footer {
    padding: 20px;
  }
}
</style>
