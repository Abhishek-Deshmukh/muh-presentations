<template lang="pug">
#ProjectProposal.eg-theme-gourmet
  .progress-bar-container
    .progress-bar(:style="`width:${currentSlideIndex/slides.length*101}vw`")
  .eg-slideshow

    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 How much to simulate?
        h4 Abhishek Anil Deshmukh
          br
          span Update 2 (6th sem project)
        eg-triggered-message(:trigger='slideTimer >= 2',
                            :duration='6', position='top right',
                            enter='bounceInRight', leave='bounceOutRight')
          p Next:
          img.control-schema(src='./assets/controlsNext.svg')
          p Previous:
          img.control-schema(src='./assets/controlsPrev.svg')
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft')
      .container-fluid
        .row(style="height:50vh;")
          h3 Outline
          ol.spaced-ul
            li Defining the problem
            li Computational approach
            li Analytical approach
            li Conclusion

    slide(enter='fadeIn' leave='bounceOutLeft')
      .container-fluid
        .row(style="height:50vh;")
          h3 Problem
          p We need to determine how much sky (cosmic background input area) to simlate because.
          ol.spaced-ul
            li Simulating too less area would be faster but would not be simulating the sky to a good enough extent.
            li Simulationg too much would be more accurate but computationally expensive
            li We need to find a sweet spot, so we need to come up with an acceptable error and simulating accordingly.
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Computational approach
      .container-fluid.mt-4
        .row
          .col-6(style="height: 70vh;")
            ul.spaced-ul
              li Simulate a 16inch*16inch*1/2inch silicon detector
              li Keep it 35 inches away from the input layer (CRY input)
              li Simulate for larger and larger dimensions of detector and see where it growth is small
          .col-6.center
            img(src="./assets/comp1_0000.png")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 Computational approach result
      .container-fluid.mt-2
        .row
          .col-6
            ul.spaced-ul
              li Simulated 10<sup>8</sup> events
              li For inputs of 10x10m<sup>2</sup> and 30x30m<sup>2</sup>
              li Took 9hrs on my laptop (each)
              li Not statistically valid at high energy
          .col-6
            img(src="./assets/all_particles_diff_10_30.png")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 Computational approach result (continued)
      .container-fluid.mt-2
        .row
          .col-6
            ul.spaced-ul
              li Lets simulate just muons
              li Again 10<sup>8</sup> events
              li For inputs of 10x10m<sup>2</sup> and 30x30m<sup>2</sup>
              li Took 7hrs on my laptop (each)
          .col-6
            img(src="./assets/10up/diff_10_30.png").half-image
            img(src="./assets/10up/diff_10_30_total.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft")
      h3 Conclusion from computational approach
      ol
        li Higher energy events are rare
        li As you increase the number of events the upper bound for the energy which will be statistically relevant will increases

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Analytical approach
      .container-fluid.mt-4
        .row
          .col-6(style="height: 70vh;")
            ul.spaced-ul
              li Keeping a detector at the origin
              li An input surface at height h
              li Lets take a point O on the input surface and calculate the solid angle projected by the detector on the point.
              li Naming points according to he image provided
          .col-6.center
            img(src="./assets/analytical_1.png").half-image
            img(src="./assets/analytical_2.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Analytical approach (continued)
      .container-fluid.mt-4
        .row
          .col-6(style="height: 70vh;")
            p Solid angle projected
            ul.spaced-ul
              li A1-A2-O make a surface, the angle between A1-A2-O and A2-A3-O will be the angle of the spherical quadrangle (.
                vue-mathjax(formula="$ \\alpha_1$")
                | )
              li Doing this for adjacent pairs of surfaces we can get the all the angles of the spherical quadrangle (
                vue-mathjax(formula="$ \\alpha_i$")
                | )
              li The solid angle projected will be
                vue-mathjax(formula='$$\\omega = \\sum_{i=1}^2{\\alpha_i} - 2\\pi$$')
          .col-6.center
            img(src="./assets/analytical_3.png")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft')
      h3 Analytical approach - Solid angle
      div(height="80vh")
        vue-mathjax(formula='$$\\omega = \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D - 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D + 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D - 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D + 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} - 2 \\pi$$')

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Analytical approach (continued)
      .container-fluid.mt-4
        .row
          .col-6
            ol
              li Now with an expression for solid angle we can integrate it for the whole input surface and calculate the fraction of particles reaching the detector.
              li The limitation being that it assumes uniform angular distribution of particles.
              li Using the above, if we calculate the input area required for the simulated case we can make the adjacent plot
              li It seems to be slowly converging to 450.
              li so with an error of 2% the input layer will have to be 1440*1440inch<sup>2</sup> which is 36.58*36.58m<sup>2</sup>.
          .col-6.center
            img(src="./assets/detector_input.png").half-image

    slide(enter='fadeIn' leave='bounceOutLeft')
      h3 Conclusion
      p In conclusion we now have a method to get an upper bound for the input layer as a function of the geometry and acceptable error.

    slide(enter='fadeIn' :steps=2)
      h3 Thank you !
      p Credits and Acknowledgements
      end-credits
      span.slide-number {{currentSlideIndex}}/{{slides.length}}
</template>

<script>
import eagle from 'eagle.js'

export default {
  data () {
    return {
      publicPath: process.env.BASE_URL
    }
  },
  mixins: [eagle.slideshow],
  infos: {
    title: 'bdm-lab Update 2 SKY',
    description: 'How much to simulate?',
    path: 'bdm-lab-update-2-sky'
  },
  components: {
    'end-credits': require('./components/EndCredits.vue').default
  }
}
</script>

<style lang='scss'>
@import 'node_modules/eagle.js/dist/themes/gourmet/gourmet';
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  src: url('../../static/fonts/Roboto-Light.ttf');
}
@font-face {
  font-family: 'Montserrat';
  font-style: normal;
  font-weight: 400;
  src: url('../../static/fonts/Montserrat-Light.ttf');
}
#ProjectProposal {
  color: black;
  .frontpage {
    width: 100%;
    h1 {
      font-size: 2.7em;
      line-height: 1.4;
      letter-spacing: -0.018em;
      font-style: normal;
      font-weight: 400;
    }
  }
  p, li, td {
    font-family: 'Roboto',serif;
    z-index: 1;
  }
  p {
    margin-bottom: 5px;
    margin-top: 10px;
  }
  table, th, td {
    border: 1px solid #aaa;
    border-collapse: collapse;
  }
  td, th {
    padding: 10px;
  }
  h1, h2, h3, h4, th {
    font-family: 'Montserrat',serif;
  }
  ul {
    margin-top: 5px;
  }
  .text-left {
    text-align: left;
  }
  .half-image {
    height: 40vh;
  }
  .quarter {
    text-align: center;
    p {
      margin-top: 0;
      text-align: center;
    }
    h4 {
      font-family: 'Montserrat';
      margin-top: 0;
      margin-bottom: 0
    }
  }
  a {
    color: black;
  }
  .half-wide {
    width: 40vw;
    margin-left: 12vw;
  }
  .background-needs {
    display: flex;
    justify-content: space-evenly;
    li {
      margin-right: 42px;
    }
  }
  .space {
    p {
      line-height: 400%;
    }
  }
  .wide-slide {
    .eg-slide-content {
      margin: 0 30px;
      width: unset;
      max-width: 100%;
    }
  }
  .spaced-ul {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }
  .slide-number {
    position: absolute;
    bottom: 10px;
    right: 15px;
  }
  .progress-bar-container {
    overflow-X: hidden;
    height: 1vh;
    bottom: 0px;
    left: 0px;
    position: absolute;
    z-index: 100;
    width: 100vw;
    .progress-bar{
      height: 100%;
      border-radius: 0vh 0.5vh 0.5vh 0vh;
      background: black;
      z-index: 100;
      transition: width 1s ease-out;
    }
  }
  .wide-flex {
    width: 100%;
    height: 100%;
  }
  .right {
    display: block;
    margin-left: auto;
  }
}
</style>
