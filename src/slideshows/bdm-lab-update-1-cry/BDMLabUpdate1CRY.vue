<template lang="pug">
#ProjectProposal.eg-theme-gourmet
  .progress-bar-container
    .progress-bar(:style="`width:${currentSlideIndex/slides.length*101}vw`")
  .eg-slideshow
    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 Simulating cosmic particles and radiation with CRY
        h4 Abhishek Anil Deshmukh
          br
          span Update 1 (6th sem project)
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
        .row
          h3 Outline
          ol
            li Cosmic-ray Shower Library (CRY)
            li CRY output analysis
            li Importing .stp format geometry into Geant4
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='fadeIn' leave='bounceOutLeft').wide-slide
      h3 Cosmic-ray Shower Library (CRY)
        sup
          a(href="https://nuclear.llnl.gov/simulation/doc_cry_v1.7/cry.pdf" target="_blank") [1]
          a(href="http://nuclear.llnl.gov/simulation" target="_blank") [2]
      .container-fluid.mt-4
        .row
          .col-6
            ul
              li Can be run stand alone or with GEANT4 or MCNP or other libraries.
              li Simulated altitudes at 0 m, 2100 m and 11300 m.
              li Covers all latitudes.
              li Accounts for comic rays due to solar activity.
              li Provides particle Energy and Momentum.
              li
                | The output is based on results from monte
                | carlo simulations of atmosphere upon photon primaries
                | across libraries like Geant4, MNCPX, Fluka.
                sup
                  a(href="https://digital.library.unt.edu/ark:/67531/metadc891037/m2/1/high_res_d/902609.pdf" target="_blank") [3]
          .col-6.center
            img(src="./assets/proton_primaries.png").half-image
            img(src="./assets/muon_spectrum.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 CRY output analysis
      .container-fluid.mt-2
        .row
          .col-6
            ul
              li Generated 10
                  sup 6
                  | events
              li in Stand alone mode.
              li Calculated the flux value from the particles produced by the library.
              li Time handling in library is not well understood.
              //li Plotting and analysis was done in
              //  |
              //  |
              //  a(href="https://www.python.org/" target="_blank") python
              //  |
              //  | with
              //  |
              //  a(href="https://matplotlib.org/" target="_blank") matplotlib
              //  |,
              //  |
              //  a(href="https://www.scipy.org/" target="_blank") scipy
              //  |
              //  | and
              //  |
              //  a(href="https://numpy.org/" target="_blank") numpy
              //  |.
              li Flux and Energy Distribution results matched with previously generated results by samir bhaiya.
            img(src="./assets/Energy_distribution.png").half-image
          .col-6.center
            img(src="./assets/Flux_2pi.png").half-image
            img(src="./assets/Flux.png").half-image
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 CRY output analysis - contd.
      .container-fluid.mt-2
        .row
          .col-6
            ul
              li Particles were not all perpendicular.
              li Incidence angle could be trivially calculated from the vector momentum of particles coming from CRY.
              li θ is the angle between momentum vector and area vector of surface.
              li The plot fit excellently (chi
                sup 2
                |/dof = 8.63E-5) with 5% error. [equation in plot]
              li The derivation for it goes here.
              li Matching with the theoretical result.
          .col-6
            img(src="./assets/Component_distribution.png")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter="fadeIn" leave="bounceOutLeft").wide-slide
      h3 Importing .stp import Geant4
      .container-fluid.mt-2
        .row
          .col-6
            h4.m-3 Problem
            ul
              li .stp files for .step files in which 3D CAD files are saved.
              li Geant4 is not capable of importing .stp or .step files directly into it's geometry
              li Input was in .stp format
            p A screenshot of it
          .col-6
            h4.m-3 Solution
            ul
              li Open the .stp file in FreeCAD
              li Export each component as .obj file
              li Import the following library into your project [
                a(href="https://github.com/christopherpoole/CADMesh") christopherpoole/CADMesh
                |].
              li Now you will be abel to import .obj files into Geant4 geometry.
            h4.m-3 Caveats
            ul
              li Conversion from .stp to .obj is very manual.
              li It can get cumbersome if the number of parts in the .stp file is too large as you will have to export each of them individually.

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
    title: 'bdm-lab Update 1 CRY',
    description: 'Simulating background with CRY',
    path: 'bdm-lab-update-1-cry'
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
    font-family: 'Roboto';
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
    font-family: 'Montserrat';
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
}
</style>
