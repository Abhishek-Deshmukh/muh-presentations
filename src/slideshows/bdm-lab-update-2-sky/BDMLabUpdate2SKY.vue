<template lang="pug">
#ProjectProposal.eg-theme-gourmet
  .progress-bar-container
    .progress-bar(:style="`width:${currentSlideIndex/slides.length*101}vw`")
  .eg-slideshow

    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 Simulating Background at MINER
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
            li Optimising the surface area of CRY to simulate.
              ul
                li Computational approach
                li Analytical approach
                li Conclusion
            li MINER background in DRU with veto detectors
              ul
                li Premise
                li Results
            li Updates on my work for MINER simulation group
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Problem
      .container-fluid
        .row
          .col-7
            p.pt-4 We need to determine surface area (cosmic background input area) to
              |
              |simulate because:
            ol
              li Simulating too less area won't be too computationally expensive
                |
                |but also won't simulating the sky to a good enough extent.
              li Simulating too much would be more close to reality but computationally
                |
                |expensive.
              p We need to find an optimised input surface area such that, it is
                |
                |accurate enough but not too computationally expensive.
              ul(style="list-style-type:none;").pt-5
                li
                  span(style="background: #99f4f4;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                  |
                  | volume to simulate
                li
                  span(style="background: #0000ff;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                  |
                  | area of the sky we simulate
                li
                  span(style="background: #808080;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                  |
                  | experiment area

          .col-5
            img(src="./assets/sufrace_area_illustration.png" style="height: 90%; margin-top: -30px;")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Computational approach
      .container-fluid.mt-4
        .row
          .col-7(style="height: 70vh;")
            p Simulation:
            ul
              li Silicon detector (cuboid)
              li cuboid dimensions: 16inch x 16inch x 1/2inch .
              li 35 inches away from the input layer (CRY input)
            img(src="./assets/computational_approach_flowchart.svg").mt-5.pt-5
          .col-5
            img(src="./assets/input_area_illustration.png" style="height: 100%;")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 Computational approach result
      .container-fluid.mt-2
        .row
          .col-6
            ul.spaced-ul
              li Simulated 10<sup>8</sup> events
              li For input surface areas of
                |
                vue-mathjax(formula="$10 \\times 10m^2$ and $30 \\times 30m^2$")
              // li Took 9hrs on my laptop (each)
              li In high energy ranges (> 100MeV) number of events is too less (< 10) and so cannot be used for statistics.
          .col-6
            img(src="./assets/all_particles_diff_10_30.png")
            p This histogram is the energy distribution of particles reaching the detector.
            ul
              li X-axis: The energy of the particle.
              li Y-axis: The number of particles which made it to the detector.
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 Computational approach result - 2
      .container-fluid.mt-2
        .row
          .col-6
            ul.spaced-ul
              li Simulating just muons for 10<sup>8</sup> events.
              li For input surface areas of
                |
                vue-mathjax(formula="$10 \\times 10m^2$ and $30 \\times 30m^2$")
              li In high energy ranges (> 100MeV) number of events is too less (0) and so cannot be used for statistics.
              // li Took 7hrs on my laptop (each)
          .col-6
            img(src="./assets/10up/diff_10_30.png").half-image
            img(src="./assets/10up/diff_10_30_total.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft")
      h3 Conclusion from computational approach
      ol
        li Higher energy events are rare.
        li Making the simulation accurate enough to get a acceptable answer, would be too computationally expensive.
        li Trying an analytical approach.
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Analytical approach
      .center
        img(src="./assets/analytical_flowchart.png")
      .container-fluid.mt-4
        .row
          .col-6
            ul
              li Keeping a detector at the origin
              li An input surface at height h
            img(src="./assets/analytical_1.png").half-image
          .col-6
            ul
              li Lets take a point O on the input surface and calculate the solid angle subtended by the detector on the point.
              li Naming points according to he image provided
            .center
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
                vue-mathjax(formula='$$\\omega = \\sum_{i=1}^4{\\alpha_i} - 2\\pi$$')
          .col-6.center.mt-5
            img(src="./assets/analytical_3.png")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3.mb-5.pb-5 Analytical approach - Solid angle
      vue-mathjax(formula='$$\\omega = \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D - 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D + 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D - 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D + 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} - 2 \\pi$$')
      .sidenote
        h5.m-0 Legend
        p
          vue-mathjax(formula='$\\omega$: the subtended solid angle')
        p
          vue-mathjax(formula='$h$: distance between the detector and input surface')
        p
          vue-mathjax(formula='$x, y$: coordinates of the point on the input surface')
        p
          vue-mathjax(formula='$D:$ length and width of the detector')
      h5(style="position: absolute;right:60px;bottom: 40px;") Step 1 complete

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
              li With an error of 2% the input layer will have to be
                |
                |
                vue-mathjax(formula="$1440 \\times 1440 inch^2$ which is $36.58 \\times 36.58 m^2$")
                | .
          .col-6.center
            img(src="./assets/detector_input.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft')
      h3 Conclusion
      p(style="margin-top: 30vh;") In conclusion we now have a method to get an upper bound for the input layer as a function of the geometry and acceptable error.
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Radiogenic simulation - Premise
      .container-fluid.mt-4
        .row
          .col-6
            h4.m-0 Premise
            ul
              li Simulated geometry for Veto
              // TODO: backup decay chain
              li Isotropic gamma radiation (Simulating radiogenic background from thorium)
              li Energy distribution of gamma from SNOLab Background data
              li Simulation to find out particle rate to simulate experimental result (~321 DRU)
              // TODO: Reference Mouli di
            img(src="./assets/crossection_12_june_0000.png")
          .col-6.center
            img(src="./assets/25_june_no_wall.png").half-image
            br
            img(src="./assets/25_june_4cm_wall.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Radiogenic simulation - Result
      .container-fluid.mt-4
        .row
          .col-7
            ul.mt-0
              li Mass of coin was 11.19g, simulation was run for
                |
                vue-mathjax(formula="$10^9$")
              li Applying a single scatter cut
                |
                |
                vue-mathjax(formula="$Edep(Donut + Top + Bottom detector) == 0$ and $Edep(Coin) > 0$")
              li
                |
                vue-mathjax(formula="$2.398 \\times 10^9$")
                | particles/day can produce 235 DRU (experimental result)
              li Now this simulation can be used to test different shielding geometries and predict the output on experimental measurement.
                |
                |
                |particles
            img(src="./assets/wall_vs_dru.png").half-image
          .col-5
            img(src="./assets/comparison_plot.png").half-image
            img(src="./assets/combines_plot.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Updates on the Simulation at SHSU
      .container-fluid
        .row
          .col-9
            p
              |
              | I integrated the .stp format geometry of a few detectors and a few
              | housings into simulation geometry and we will be starting to run
              | simulations from this or next week.
            .container-fluid
              .row
                .col-6
                  img(src="./assets/crossection_cartoon.png").mt-5.pt-5
                .col-6.toggle
                  img(src="./assets/27_june_crossection_complete_colored_front_0000.png").l-90.hide-on-hover.toggle-1
                  img(src="./assets/27_june_crossection_complete_colored_angled_0000.png").l-90.toggle-2
          .col-3
            ul(style="list-style-type:none;").pt-5
              li
                span(style="background: #6b0404;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | All housings
              li
                span(style="background: #15ffff;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | Veto of the veto detector
              li
                span(style="background: #00ff00;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | Coin of the veto detector
              li
                span(style="background: #ff0004;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | Spool and it's adapter
              li
                span(style="background: #9e3ea5;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | Electrodes
              li
                span(style="background: #0b1bff;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | S26 detector (silicon)
              li
                span(style="background: #fff70a;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | HV detector
              li
                span(style="background: #005500;width: 20px; height: 20px;display: inline-block;border: 1px solid black;")
                |
                | Hybrid Detector
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

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
    li {
      font-size: 0.9em;
    }
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
  .sidenote {
    position: absolute;
    bottom: 0;
    left: 0;
    padding: 40px 25px;
    margin: 40px 25px;
    border: 1px solid black;
  }
  .l-90 {
    transform: rotate(-90deg);
  }
  .toggle {
    .toggle-1 {
      display: inline;
    }
    .toggle-2 {
      display: none;
    }
    &:hover {
      .toggle-1 {
        display: none;
      }
      .toggle-2 {
        display: inline;
      }
    }
  }
}
</style>
