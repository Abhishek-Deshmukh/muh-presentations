<template lang='pug'>
.slide-number-container
  .line
  .circle
    .current-number {{slide_number}}
    .final-number 11
</template>

<script>
export default {
  props: {
    slide_number: Number
  }
}
</script>

<style lang='scss' scoped>
  .slide-number-container {
    position: absolute;
    height: 70px;
    width: 70px;
    right: 50px;
    top: 50px;
    .line {
      position: absolute;
      padding-bottom: 12px;
      background: white;
      width: 1px;
      height: 58px;
      transform: rotate(45deg);
      margin-left: 37px;
      margin-top: 3px;
    }
    .circle {
      border-radius: 50%;
      height: 100%;
      width: 100%;
      border: 1px solid white;
      .current-number {
        font-size: 30px;
        margin-left: 10px;
        margin-top: 4px;
      }
      .final-number {
        font-size: 24px;
        margin-left: 32px;
        margin-top: -5px;
      }
    }
  }
</style>
