<template lang="pug">
#ProjectProposal.eg-theme-agrume
  .progress-bar-container
    .progress-bar(:style="`width:${currentSlideIndex/slides.length*101}vw`")
  .eg-slideshow
    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 Understanding Backgrounds for Rare-Event searches
        h4 Abhishek Anil Deshmukh
          br
          span 6th sem Project Proposal
        eg-triggered-message(:trigger='slideTimer >= 2',
                            :duration='6', position='top right',
                            enter='bounceInRight', leave='bounceOutRight')
          p Next:
          img.control-schema(src='./assets/controlsNext.svg')
          p Previous:
          img.control-schema(src='./assets/controlsPrev.svg')
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=4 enter='bounceInRight' leave='bounceOutLeft').wide-slide
      h3 Rare Event
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        img(v-if="step>=2" src="./assets/rare_event.png").cross-section-plot
      .container-fluid
        .row.center
          .col-8
              eg-transition(enter='bounceInRight' leave='bounceOutRight')
                p(v-if="step>=2") Rare events are events that happen only a few times over a long period of time.
              eg-transition(enter='bounceInRight' leave='bounceOutRight')
                p(v-if="step>=2") Like in the case of SuperCDMS, with 15 germanium detectors about 600g each reached
                  |
                  |a cross-section
                  |
                  |of 10<sup>-41</sup>cm<sup>2</sup> for a mass of ~ 10GeVc<sup>-2</sup> with 95% CL.
                  a(href="https://www.slac.stanford.edu/exp/cdms/ScienceResults/Publications/PhysRevD.97.022002.pdf" target="_blank") [1]
              eg-transition(enter='bounceInRight' leave='bounceOutRight')
                p(v-if="step>=3") Examples of such rare interactions would include Coherent Elastic Neutrino Nucleus S
                  |cattering(CEνNS), Dark matter Interactions, neutrino less double beta decay.
              eg-transition(enter='bounceInRight' leave='bounceOutRight')
                p(v-if="step>=4") Some examples of experiments that search for rare events are:
                  ul
                    li <b>MINER</b> (CEνNS, Sterile Neutrino)
                    li <b>SuperCDMS</b>. (Dark matter)
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=5, enter='bounceInRight' leave='bounceOutLeft').MINER
      h3
        img(src="./assets/niser_logo.jpg").niser_logo
        | MINER
        img(src="./assets/texas_A_and_M.jpg").texas_anm_logo
      .container-fluid
        .row
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            p(v-if="step >= 2") Mitchell Institute Neutrino Experiment at Reactor
          eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
            p(v-if="step >= 3") Located at Nuclear Science Center in Texas A & M University
          .col-6
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if="step >= 4") Searching for Coherent Elastic Neutrino Nucleus Scattering (CEνNS)
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if="step >= 5") By placing low threshold, cryogenic germanium and silicon
                |
                |detectors a few meters from the reactor core.
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(v-if="step >= 4" src="./assets/CEvNS.jpg" alt="CEνNS")
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=5, enter='bounceInRight' leave='bounceOutLeft')
      h3 Lets break it down

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=2')
          img(src='./assets/icons/basic_share.svg')
          h4 The Reactor
          p 1MW TRIGA reactor

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=3')
          img(src='./assets/icons/basic_paperplane.svg')
          h4 The signal
          p Neutrino-Nucleus Scattering

      eg-transition(enter='fadeIn' leave='fadeOut')
        div(style="border: solid 1px black;border-radius: 15px;padding:10px;" v-if="step >= 4")
          eg-transition(enter='fadeIn' leave='fadeOut')
            .quarter(v-if="step >= 4")
             img(src='./assets/icons/basic_mixer2.svg')
             h4 Backgrounds
             p Cosmogenic and Radiogenic backgrounds

          eg-transition(enter='fadeIn' leave='fadeOut')
            .quarter(v-if="step >= 5")
              img(src='./assets/icons/basic_display.svg')
              h4 The Simulation
              p GEANT4 and MCNP
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=8, enter='bounceInRight' leave='bounceOutLeft')
      h3 The Reactor
      .center
        eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
          p(v-if='step >= 2') 1MW TRIGA Reactor
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if='step >= 3') Training, Research, Isotopes, General Atomics
      .container-fluid
        .row
          .col-6
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if='step >= 4') Filled with 20% <sup>235</sup>U
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if='step >= 5') Uranium Decay causes release of
            ul.text-left
              eg-transition(enter='fadeIn' leave='fadeOut')
                li(v-if='step>= 6') Neutrino (Signal)
              eg-transition(enter='fadeIn' leave='fadeOut')
                li(v-if='step>= 7') Gamma, alpha, beta (Background)
              eg-transition(enter='fadeIn' leave='fadeOut')
                li(v-if='step>= 8') Creates a Neutrion Flux of 3.73 x 10<sup>11</sup> neutrino/cm<sup>2</sup>/s at 2m
                  a(:href="`${publicPath}sharada_project_Update_1.pdf`" target="_blank") [2]
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(v-if='step >= 4' alt="Uranium Decay Chain" src="./assets/uranium_decay_chain.png").u-chain
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=8, enter='bounceInRight' leave='bounceOutLeft')
      h3 The Signal
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        img(src="./assets/CEvNS.jpg" v-if="step >= 3").cevns
      .center
        eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
          p(v-if='step >= 2') Caused by CEνNS (Coherent Elastic Neutrino Nucleus Scattering)
            a(href="https://journals.aps.org/prd/pdf/10.1103/PhysRevD.9.1389" target="_blank") [4]
      .container-fluid
        .row
          eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
            .col-3(v-if='step >= 3')
              Neutrino(:energy="1")
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            .col-7(v-if='step >= 3').half-wide
              p.coherent <b>Coherent</b>: Interaction with the nucleus as a whole. Requires the neutrino to have
                |
                | energy of the order of tens of MeV.
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if='step >= 4') <b>Elastic</b> implies conservation of Energy and Momentum.
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if='step >= 5') These interactions cause:
        ul
          eg-transition(enter='fadeIn' leave='fadeOut')
            li(v-if='step>=6') Neutrino Scattering
          eg-transition(enter='fadeIn' leave='fadeOut')
            li(v-if='step>=7') Nuclear Recoil (Recorded in the form in deposited energy) (THE SIGNAL)
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if="step >=8") Expected event rate ~ 0.488/day
            a(:href="`${publicPath}sharada_project_Update_1.pdf`" target="_blank") [2]
            |
            | at 2 meters for a 100g Si detector
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=7 enter='bounceInRight' leave='bounceOutLeft')
      h3 Backgrounds and Problem
      .center
        p Anything other than neutrinos that can deposit energy in the detector is background.

      .container-fluid
        .row
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            .col-5(v-if='step>=2')
              ul.spaced-ul
                li Alpha
                li Beta
                li Gamma
                li Muon
                li Neutron
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            .col-7(v-if='step >=2')
              img(src="./assets/background_to_signal_representation.png" style="height: 38vh;")
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=4') Background needs to be
      ul.background-needs
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if='step>=5') Understood
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if='step>=6') Reduced
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if='step>=7') Rejected
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=5 enter='bounceInRight' leave='bounceOutLeft')
      h3 Background
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=2') To reduce backgrounds from reaching the detector:
      .container-fluid
        .row
          .col-5.space
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              p(v-if='step>=3') Shielding Material
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              p(v-if='step>=4') Shielding Geometry
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              div(v-if='step>=2')
                a(:href="`${publicPath}MINER_paper.pdf`" target="_blank") [3]
                img(src="./assets/experiment_site.png" style='transform:scale(2); margin-left: 40%;margin-top: 20%;')
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=5') Statistical methods like likelihood analysis make use of background models which can
          |
          |be obtained from simulations
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(:steps=3 enter='bounceInRight' leave='bounceOutLeft')
      h3 Simulation
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=2').center We use <b>GEANT4</b> as the framework for Simulation.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=2').center GEANT4 is a toolkit for the simulation of the passage of particles through
          |
          | matter. Its areas of application include high energy, nuclear and accelerator physics,
          |
          |as well as studies in medical and space science.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=3') I was able to simulate the following geometry:
      .container-fluid
        .row
          .col-3
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(src="./assets/G4detector.png" alt="Image of geometry" v-if='step>=3')
          .col-9
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              table(v-if="step>=3")
                tr
                  th Geometry
                  th Material
                  th Inner Radius
                  th Outer Radius
                  th Thickness
                tr
                  td Cylinder
                  td Germanium
                  td -
                  td 12.7mm
                  td 4mm
                tr
                  td Cylinder
                  td Silicon
                  td 12.7mm
                  td 38.1mm
                  td 25.4mm
      span.slide-number {{currentSlideIndex}}/{{slides.length}}

    slide(enter='bounceInRight' :steps=6 leave='bounceOutLeft')
      h3 Proposal
      ol
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if="step>=2") Understanding background and optimizing shielding parameters for better reduction in MINER.
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if="step>=3") Sterile Neutrino Search using MINER and CEvNS.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        h3(v-if="step>=4") Steps
      ol
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if="step>=4") Defining MINER geometry with GEANT4
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if="step>=5") Estimating cosmogenic and radiogenic backgrounds at MINER.
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          li(v-if="step>=6") Study Sterile Neutrino.

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
    title: '6th Sem Project Proposal',
    description: 'Background study in MINER',
    path: '6th-sem-project-proposal'
  },
  components: {
    'Neutrino': require('./components/Neutrino').default,
    'end-credits': require('./components/EndCredits.vue').default
  }
}
</script>

<style lang='scss'
@import 'node_modules/eagle.js/dist/themes/agrume/agrume';
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
  .MINER {
    background-image: url("./assets/Nuclear_Science_Center.png");
    background-repeat: no-repeat;
    background-size: auto 100%;
    background-position: center;
    p, h3 {
      background-color: white;
    }
    .texas_anm_logo {
      position: absolute;
      height: 1.6em;
      margin-left: 20%;
    }
    .niser_logo {
      position: absolute;
      height: 1.6em;
      margin-left: -26%;
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
  .cevns {
    position: absolute;
    right: 20px;
    top: 20px;
    width: 20vw;
  }
  ul {
    margin-top: 5px;
  }
  .text-left {
    text-align: left;
  }
  .coherent {
    line-height: 1.1;
    margin-bottom: -0.36px;
    margin-top: 15.64px;
  }
  .u-chain {
    position: absolute;
    width: 42%;
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
  .cross-section-plot {
    position: absolute;
    right: 20px;
    top: 30vh;
    width: 30vw;
    z-index: 0;
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
