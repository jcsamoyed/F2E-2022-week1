<template>
  <button :class="theme"><slot></slot></button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    theme: {
      type: String,
      default: 'orange',
    },
  },
};
</script>

<style lang="scss" scoped>
button {
  font-size: 16px;
  color: #fff;
  padding: 8px 40px;
  border: none;
  border-radius: 64px;
  cursor: pointer;
  &.orange {
    background-color: #f47924;
  }
}
</style>
