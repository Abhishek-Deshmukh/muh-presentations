<template lang='pug'>
.end-credits-container
  .end-credits
    .end-credit-category(v-for='category, name in categories')
      h4.center {{ name.toUpperCase() }}
      .end-credit-line(v-for='person in category')
        p.left {{ person.name }}
        p.right {{ person.role }}
</template>

<script>
export default {
  data: function () {
    return {
      categories: {
        'Credits': [
          {
            name: 'Abhishek Anil Deshmukh',
            role: 'Presenter & Author'
          },
          {
            name: 'Bedangadas Mohanty & Lab',
            role: 'Project guidance'
          }
        ],
        'References': [
          {
            name: '[1]',
            role: 'SuperCDMS\'s SNOLAB'
          },
          {
            name: '[2]',
            role: 'Sharada\'s Project Update 1'
          },
          {
            name: '[3]',
            role: 'MINER Paper'
          },
          {
            name: '[4]',
            role: 'Phys. Rev. D 9(1974)'
          }
        ],
        'Software': [
          {
            name: 'Vue.js',
            role: 'Front-end engine'
          },
          {
            name: 'Eagle.js',
            role: 'Slideshow framework'
          },
          {
            name: 'Animate.css',
            role: 'Transitions animations'
          },
          {
            name: 'Hammer.js',
            role: 'Swipe events'
          }
        ]
      }
    }
  }
}
</script>
<style lang='scss' scoped>
@import url(https://fonts.googleapis.com/css?family=Patrick+Hand+SC);
@keyframes scroll {
    from {margin-top: 0%}
    to {margin-top: -500%}
}
.end-credits-container{
  height: 11em;
  font-family: 'Patrick Hand SC';
  overflow-y: hidden;
  border-top: 1px solid grey;
  border-bottom: 1px solid grey;

  .end-credits {
    font-size: 0.9em;
    padding-top: 50%;

    .end-credit-category {
      .end-credit-line {
        p {
          margin-top: 0
        }
        .left {
          width: 45%;
          margin-right: 10%;
          text-align: right;
          display: inline-block;
        }
        .right {
          display: inline-block;
          text-align: right;
        }
      }
    }
    animation-name: scroll;
    animation-duration: 34s;
    animation-timing-function: linear;
    -webkit-animation-timing-function: linear;
    &:hover {
      animation-play-state: paused;
    }
  }
}
</style>
