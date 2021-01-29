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
            role: 'Presenter'
          },
          {
            name: 'Samir Banik & Vijay Iyer',
            role: 'PhD guidance'
          },
          {
            name: 'Sarada',
            role: 'Flux Data'
          },
          {
            name: 'Abhishek Anil Deshmukh',
            role: 'Author'
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
        ],
        'Assets': [
          {
            name: 'Irfan iLias',
            role: 'Background Pattern'
          },
          {
            name: 'Paper "Background study for MINER"',
            role: 'Reactor Pool Schem-view'
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
    animation-duration: 24s;
    animation-timing-function: linear;
    -webkit-animation-timing-function: linear; /* Safari 4.0 - 8.0 */
  }
}
</style>
