<template>
  <button class="v-button">按钮</button>
</template>

<script>
export default {}
</script>

<style lang="less">
.v-button {
  font-size: 14px;
  height: 32px;
  padding: 0 1em;
  border-radius: 5px;
  border: 1px solid #999;
  background: #fff;
  &:hover {
    border-color: #666;
  }
  &:active {
      background-color: #eee;
  }
  &:focus {
      outline: none;
  }
}
</style>