<template lang="pug">
.eg-slideshow#ProjectEvaluation

  slide(enter='fadeIn' :steps=3).cover-slide
    eg-transition(enter='none' leave='fadeOutLeft')
      h1.title(v-if='step===1') Background simulations <br /> for MINER
    eg-transition(enter='fadeInUp' leave='fadeOutLeft')
      p.subtext(v-if='step===1') 6th semester project evaluation
    eg-transition(enter='fadeInUp' leave='fadeOutLeft')
      p.subtext(v-if='step===1') Abhishek Anil Deshmukh (1811004)
    eg-transition(enter='fadeInUp' leave='fadeOutLeft')
      p.subtext(v-if='step===1').mt-5.pt-5 Supervisor: Dr. Bedangadas Mohanty
    eg-transition(enter='fadeInUp' leave='fadeOutLeft')
      p.subtext(v-if='step===1') Co.Supervisor: Dr. Varchaswi K S Kashyap

    eg-transition(enter='fadeInUp')
      h1(v-if='step===3') Outline
    .container
      ul.TOC
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') CEνNS
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') MINER
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') Cosmogenic Background
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') Radiogenic Background
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') Effects of Pb Shielding
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') Contributions
        eg-transition(enter='fadeInUp')
          li(v-if='step===3') Conclusion
    img(src="./assets/white_logo.png").niser-logo

  slide(enter='fadeIn' :steps=5)
    slide-number(slide_number=2)
    h1 CEνNS
      a(href="https://journals.aps.org/prd/pdf/10.1103/PhysRevD.9.1389" target="__blank").reference [1]
    .container-fluid
      .row
        .col-6.ps-5
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2') Coherent elastic neutrino nucleus scattering.
          ul
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===2') <strong>Coherent</strong>: Interaction with
                |
                | the nucleus as a whole. Requires the neutrino to have energy
                | in range of 10s of MeVs.
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===2') <strong>Elastic</strong>: Conserves energy an
                |d momentum.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p.mb-0(v-if='step===2') Such an interaction causes:
          ul.mt-2(v-if='step<=3')
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===2') Neutrino Scattering
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===2') Nuclear Recoil
          eg-transition(enter='fadeInRight' leave='fadeOutLeft')
            p(v-if='step===4') CEνNS interactions are rare.
          eg-transition(enter='fadeInRight' leave='fadeOutLeft')
            p(v-if='step===4') Crosssection between neutrino and Si atom is less than order -42 per cm<sup>2</sup>.
             a(href="https://arxiv.org/pdf/1510.00999.pdf" target="__blank").reference [2]
          .neutrino-container
            eg-transition(leave='slide')
              neutrino.mt-5
        .col-6.center
          eg-transition(enter='fadeInUp' leave='fadeOutDown')
            img(src="./assets/CEvNS.jpg" v-if='step===2||step===3 || step===4').cenns

  slide(enter='fadeIn' :steps=5)
    slide-number(slide_number=3)
    h1 MINER
    .container-fluid
      .row
        .col-6.ps-5
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2').mt-3.mb-4 Mitchell Institute Neutrino Experiment at
              |
              |Reactor
              a(href="https://arxiv.org/pdf/1510.00999.pdf" target="__blank").reference [3]
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2').mt-5.mb-0 Dedicated to measuring CEvNS.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2').mt-0 By placing low energy threshold cryogenic
              |
              | germanium and silicon detectors a few meters from the reactor core.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2').mb-2 Uses 1MW TRIGA reactor, fuelled with Lightly enriched Uranium.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2 || step === 3 || step ===4').mt-2 100g
              |
              | Si detector at 2m receives a flux of
              |
              vue-mathjax(formula="$3.73\\times 10^{11}$ neutrino/cm$^2$/s")
              |
              | which translates to ~ 0.448 events/day.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===4').mb-3 Neutrinos aren't the only particles
              |
              | depositing energy on the detector.
          ul.mt-0
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===4') muons
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===4') gamma
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===4') alpha
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===4') beta
            eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
              li(v-if='step===4') neutrons
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            img(src='./assets/white_logo.png' v-if='step===2').niser-logo-bl
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===4').mb-3 These backgrounds can be classified into
              |
              |2 categories based on their sources: Cosmogenic, and Radiogenic.
        .col-6
          eg-transition(enter='fadeInRight' leave='fadeOutRight')
            img(src='./assets/Nuclear_Science_Center.png' v-if='step===2').nsc
          eg-transition(enter='fadeInRight' leave='fadeOutRight')
            span(v-if='step===2').nsc-caption Nuclear Science Center in Texas A&M University
          eg-transition(enter='fadeInRight' leave='fadeOutRight')
            img(src='./assets/TAM-Logo-white.png' v-if='step===2').tam-logo
          eg-transition(enter='fadeInRight' leave='fadeOutRight')
            img(src='./assets/background_to_signal_representation.png' v-if='step===4').nsc.invert

  slide(enter='fadeIn' leave='fadeOut' :steps=8).cosmo
    slide-number(slide_number=4)
    h1 Cosmogenic Background
    .container-fluid
      .row
        .col-6.ps-5
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step>=2 && step <=7').mt-2.mb-0 Consists of cosmic ray showers.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step>=2 && step <=7').mt-4.mb-0 Simulated by Cosmic-ray Shower Library
              |
              |(CRY).
              a(href="https://nuclear.llnl.gov/simulation/doc_cry_v1.7/cry.pdf" target="__blank").reference [5]
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step>=2 && step <=7').mt-0.mb-3 The output is based on simulations of atmosphere
              |
              |with cosmic-ray primaries.
              a(href="https://www.osti.gov/servlets/purl/902609/" target="__blank").reference [4]
          img(src="./assets/Flux_2pi.png" v-if='step===2').flux
          img(src="./assets/Component_distribution.png" v-if='step===2').comp-dist
          eg-transition(enter='none' leave='fadeOutLeft')
            p(v-if='step>=3 && step <=7').mb-1.mt-3 CRY considers changes due to:
          ul.mt-1.mb-0
            eg-transition(enter='none' leave='fadeOutLeft')
              li(v-if='step >=3 && step <=7') Solar cycle
            eg-transition(enter='none' leave='fadeOutLeft')
              li(v-if='step>=4 && step <= 7') Latitude
            eg-transition(enter='none' leave='fadeOutLeft')
              li(v-if='step>=5 && step <= 7').mb-0.pb-0 Altitude
          eg-transition(enter='none' leave='fadeOutLeft')
            p(v-if='step===6 || step===7 ').mt-3.mb-2 It simulates the specified surface area of the sky.
          eg-transition(enter='none' leave='fadeOutLeft')
            p(v-if='step==7').mt-3 We need to find an optimised input surface are
              |a such that, it is accurate enough but not too computationally
              |expensive.

        .col-6.center
          img(src='./assets/muon_spectrum.png' v-if='step===2').single-image
          a(href="https://www.osti.gov/servlets/purl/902609/" v-if='step===2' target="__blank").reference [4]
          img(src='./assets/proton_primaries.png' v-if='step===3').single-image
          a(href="https://www.osti.gov/servlets/purl/902609/" v-if='step===3' target="__blank").reference [4]
          img(src='./assets/latitudes.jpg' v-if='step===4').single-image
          ul(v-if='step===5' style='list-style: none;')
            li 0m
            li 2100m
            li 11300m
          img(src='https://i.imgur.com/4wslofw.png' v-if='step===6').single-image
          eg-transition(enter='none' leave='fadeOutRight')
            img(src='./assets/sufrace_area_illustration.png' v-if='step===7' style='margin-top: -180px;').single-image

  slide(enter='fadeIn' leave='fadeOut' :steps=2).cosmo
    slide-number(slide_number=5)
    h1 Computational Approach
    .container-fluid
      .row
        .col-6.ps-5
          p.mb-3 Simulation:
          ul.mt-3
            li Silicon detector (16inch X 16inch X .5inch cuboid)
            li 35 inches away from the input layer
          p Run the simulation for incremental surface areas till the detector
            |
            |input saturates.
          eg-transition(enter='fadeInLeft' leave='fadeOutLeft')
            p(v-if='step===2') Higher energy events were too low in count to be statistically reliable.
        .col-6.center
          img(src="./assets/input_area_illustration.png" v-if='step==1')
          eg-transition(enter='fadeInRight' leave='fadeOutRight')
            img(src="./assets/diff_10_30.png" v-if='step===2').single-image.mt-5

  slide(enter='fadeIn' leave='fadeOut' :steps=4).cosmo
    slide-number(slide_number=6)
    h1 Analytical Approach
    .center
      img(src="./assets/analytical_1.png" v-if='step===1' style='width: 60vw;').mt-5
    .container-fluid(style='padding-top:4vh;')
      vue-mathjax(formula='$$\\omega = \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D - 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D - 2 x\\right) \\left(D + 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D - 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D - 2 y\\right)}{ \\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D - 2 y\\right)^{2}}} \\right)} + \\operatorname{acos}{\\left(\\frac{\\left(D + 2 x\\right) \\left(D + 2 y\\right)}{\\sqrt{4 h^{2} + \\left(D + 2 x\\right)^{2}} \\sqrt{4 h^{2} + \\left(D + 2 y\\right)^{2}}} \\right)} - 2 \\pi$$' v-if='step>=2')
      .sidenote(v-if='step>=2').mt-5.pt-3.ps-5
      p
        vue-mathjax(formula='$\\omega :$ the subtended solid angle')
      p
        vue-mathjax(formula='$h:$ distance between the detector and input surface')
      p
        vue-mathjax(formula='$x, y:$ coordinates of the point on the input surface')
      p
        vue-mathjax(formula='$D:$ length and width of the detector')
      img(src="./assets/analytical_1.png" v-if='step===2').bottom-right
      img(src="./assets/detector_input.png" v-if='step>=3' style='background: white;').bottom-right
      .result-container(v-if='step>=4')
        p.heading Result
        p.result The MINER setup with input layer at 35 inches from the
          |
          |detector needs a
          |
          vue-mathjax(formula='$36.58\\,m \\times 36.58\\,m$')
          |
          | input surface to simulate the cosmic-ray shower with 98%
          |accuracy.

  slide(enter='fadeIn' leave='fadeOut').radio
    slide-number(slide_number=7)
    h1 Radiogenic Background
    .container-fluid
      .row
        .col-6.ps-5
          p Recorded gamma background from SNOLAB is used to predict the energy of a particle.
          p Primarily gamma background, also called as ambient gamma.
          p The background need to be isotropic in nature.
        .col-6.center
          img(src="./assets/total_background.png").single-image

  slide(enter='fadeIn' leave='fadeOut' :steps=8).radio
    slide-number(slide_number=8)
    h1 Effects of Pb Shielding
    .pop-up(v-if='step===4')
      span.title Aim
      br
      span.question Experimental measurements show a particle rate of 303 DRU,
        |
        |what thickness of shielding would turn the particle rate to under 50
        |DRU?
    .pop-up(v-if='step===8')
      span.title Result
      br
      span.question 2cm thickness of lead shielding will decrease the particle rate from 303 DRU to 46 DRU.
    .container-fluid.ps-3
      .row
        .col-6
          p(v-if='step>=1') Detector veto
          img(src="./assets/detector3.png" v-if='step===1').single-image
          p(v-if='step>=2') Geant4 simulation
          p(v-if='step>=3') Cubic Lead Shielding on 5 sides
          p(v-if='step>=5') Step 1: Calibration
          p(v-if='step>=6') Step 2: Run the simulation for different wall thicknesses.
          p(v-if='step>=7') Step 3: Compare results
        .col-6.center
          img(src="./assets/detector1.png" v-if='step===1').single-image
          // p(v-if='step===1') Importing CAD files into Geant4
          // ul(v-if='step===1' style='text-align: left;')
            li Export the geometry in .stp format
            li Open the .stp file in FreeCAD
            li Import CADMesh into your project
            li You can now import .obj files into Geant4
          img(src="./assets/25_june_no_wall.png" v-if='step===2').single-image
          img(src="./assets/25_june_4cm_wall.png" v-if='step===3 || step===4').single-image
          ul(v-if='step===5' style='text-align: left;')
            li Ran the simulation for 10<sup>9</sup> particles
            li Add normal noise
            li Apply a single scatter cut
            li Result: 2.398 x 10<sup>6</sup> particles will simulate a day's worth of particles.
          img(src="./assets/nowall_ssc_100_300_with_noise.png" v-if='step===5' style='width: 35vw;')
          ul(v-if='step===6' style='text-align: left;')
            li 2cm
            li 4cm
            li 6cm
            li 8cm
          img(src="./assets/combines_plot.png" v-if='step>=7').double-image-up
          img(src="./assets/wall_vs_dru.png" v-if='step>=7').double-image-down

  slide(enter='fadeIn' leave='fadeOut')
    slide-number(slide_number=9)
    h1 Contributions to the MINER Simulation team
    .container-fluid
      .row
        .col-9.center
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

  slide(enter='fadeIn' leave='fadeOut')
    slide-number(slide_number=10)
    h1 Conclusions
    .container
      ol.spread-list
        li Analysis of CRY output showed angular distribution of muons follows
          |
          vue-mathjax(formula=' $ cos^3(\\theta)sin(\\theta) $ ')
          |
          |distribution.
        li Made an integral that can be used to calculate dimensions of the input surface of CRY.
        li Made a procedural method to import CAD files into Geant4.
        li Made a model simulation which can now be used to test a variety of shieldings.
        li A cuboidal 2cm lead shielding with one side open decreases the particle rate from 303 DRU to 46 DRU.
        li Contributed Geometry building at MINER simulation team.

  slide(enter='fadeIn' :steps=2)
    slide-number(slide_number=11)
    h3 Thank you !
    .container
      p Credits and Acknowledgements
      end-credits
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
    title: '6th sem project evaluation',
    description: 'Background simulations for MINER',
    path: '6th-sem-project-evaluation'
  },
  components: {
    'end-credits': require('./components/EndCredits.vue').default,
    'slide-number': require('./components/SlideNumber').default,
    'neutrino': require('./components/Neutrino').default
  }
}
</script>

<style lang='scss'>
  @font-face {
    font-family: 'Roboto';
    src: url('./assets/Roboto-Medium.ttf');
  }
  @font-face {
    font-family: 'Roboto-light';
    src: url('../../static/fonts/Roboto-Light.ttf');
  }
  #ProjectEvaluation {
    background: #181818;
    color: #ddd;
    font-family: Roboto-light;
    .eg-slide {
      width: 1920px;
      height: 1080px;
    }
    .cover-slide {
      .title {
        font-family: Roboto;
        text-align: left;
        font-size: 85px;
        margin-top: 228px;
        margin-left: 111px;
        font-weight: 500;
        margin-bottom: 2em;
      }
      .subtext {
        margin-left: 100px;
        margin-top: 0px;
        margin-bottom: 0px;
        font-size: 40px;
      }
    }
    .niser-logo {
      position: absolute;
      width: 60vh;
      height: 63vh;
      right: 100px;
      bottom: 100px;
      /* opacity: 0.3; */
    }
    h1 {
      font-family: Roboto;
      font-weight: 500;
      font-size: 85px;
      text-align: left;
      margin-top: 100px;
      margin-left: 100px;
    }
    .TOC {
      list-style-type: none;
      li {
        margin-bottom: 30px;
      }
    }
    .cenns {
      height: 81vh;
    }
    .neutrino-container {
      position: absolute;
      width: 40vw;
      height: 400px;
      bottom: -50px;
      left: 0px;
    }
    .nsc {
      position: absolute;
      width: 50vw;
      right: 0px;
      top: 180px;
    }
    .nsc-caption {
      position: absolute;
      font-size: 35px;
      right: 180px;
      bottom: 70px;
    }
    .tam-logo {
      position: absolute;
      width: 170px;
      bottom: 15px;
      right: 0px;
    }
    .niser-logo-bl {
      position: absolute;
      width: 170px;
      bottom: 15px;
      left: 50px;
    }
    .invert {
      -webkit-filter: invert(1);
      filter: invert(1);
    }
  }
  .cosmo {
    background: #282a36;
    color: #f8f8f2;
    .pink {
      color: #ff79c6;
    }
  }
  .radio {
    background: #002b36;
    color: #839496;
  }
  .single-image {
    width: 40vw;
  }
  .bottom-right {
    position: absolute;
    width: 40vw;
    bottom: 0px;
    right: 0pc;
  }
  .result-container {
    position: absolute;
    width: 80vw;
    height: 30vh;
    left: 10vw;
    top: 30vh;
    background: #282a36;
    display: block;
    border: 1px solid white;
    padding: 20px 70px 0px 50px;
    .heading {
      font-weight: 900;
      font-size: 67px;
      margin-top: 8px;
      margin-bottom: 31px;
    }
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

  .l-90 {
    transform: rotate(-90deg);
  }
  .pop-up {
    position: absolute;
    width: 70vw;
    height: 20vh;
    background: #002b36;
    left: 15vw;
    top: 20vh;
    padding: 40px;
    border: 1px solid white;
    .title {
      font-size: 77px;
    }
  }
  .double-image-up {
    width: 31vw;
    margin-top: -50px;
    &:hover {
      width: 50vw;
      position: absolute;
      top: 10vh;
      left: 25vw;
      z-index: 100;
    }
  }
  .double-image-down {
    width: 31vw;
    position: absolute;
    right: 8.4vw;
    top: 55vh;
    &:hover {
      width: 50vw;
      top: 10vh;
      left: 25vw;
      z-index: 100;
    }
  }
  .spread-list {
    li {
    margin-top: 30px;
    }
  }
  .flux {
    width: 25vw;
    position: absolute;
    left: 10px;
    &:hover{
      width: 50vw;
      top: 10vh;
      left: 5vw;
      z-index: 100;
    }
  }
  .comp-dist {
    position: absolute;
    width: 26vw;
    left: 27vw;
    &:hover{
      width: 50vw;
      top: 10vh;
      left: 25vw;
      z-index: 100;
    }
  }
  .reference {
    opacity: 20%;
    color: white;
    vertical-align: sub;
    font-size: 30px;
  }
</style>
