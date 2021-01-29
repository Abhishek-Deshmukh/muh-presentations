<template lang='pug'>
#app
  router-view
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="scss">
@import './static/bootstrap/bootstrap-grid.scss';
body, html {
  width: 100vw;
  margin: 0px;
  font-family: 'Fira Code';
  color: white;
  background: #232323;
}
@font-face {
  font-family: 'Fira Code';
  font-style: normal;
  font-weight: 400;
  src: url(./static/fonts/FiraMono-Regular.otf);
}
</style>
