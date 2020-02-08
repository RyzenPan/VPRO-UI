<template>
  <svg class="icons">
      <use :xlink:href="`#icon-${name}`" />
    </svg>
</template>

<script>
export default {
    props:['name']
}
</script>

<style>
  .icons {
    width: 1em;
    height: 1em;
    margin-right: 0.4em;
  }
</style>