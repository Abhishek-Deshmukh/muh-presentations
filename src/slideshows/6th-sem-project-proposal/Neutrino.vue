<template lang="pug">
div
  .neutrino(:style="'animation-duration:' + 1/energy + 's;'")
  .line(:style="'margin-top: 30px; z-index: 0; animation-duration:' +  1.6/energy + 's;'")
  .line(:style="'margin-top: 60px; z-index: 2; animation-duration:' + 1.2/energy +'s;'")
  .line(:style="'margin-top: 104px; z-index: 0; animation-duration:' + 2/energy +'s;'")
  .line(:style="'margin-top: 134px; z-index: 0; animation-duration:' + 1/energy +'s;'")
</template>
<script>
export default {
  name: 'Neutrino',
  props: {
    energy: {
      type: Number,
      default: 1
    }
  }
}
</script>
<style scoped lang="scss">
@keyframes vibration {
  0% {
    margin-top: 60px;
  }
  50% {
    margin-top: 40px;
  }
  100% {
    margin-top: 60px;
  }
}

@keyframes moving-bg {
  0% {
    right: 50%;
  }
  100% {
    right: 100%;
  }
}
.neutrino {
  z-index: 1;
  margin-top: 50px;
  width: 70px;
  height: 70px;
  background: #4d4dc4;
  border-radius: 50%;
  animation-name: vibration;
  animation-iteration-count: infinite;
  position: absolute;
}
.line {
  position: absolute;
  width: 130px;
  height: 1px;
  border-radius: 50%;
  background: #eee;
  animation-name: moving-bg;
  animation-duration: 1.2s;
  animation-iteration-count: infinite;
}
</style>
