<template lang="pug">
#ProjectProposal.eg-theme-agrume
  .eg-slideshow
    slide(enter='fadeIn' leave='bounceOutLeft')
      .center.frontpage
        h1 Understanding Background for Rare-Event searches
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

    slide(:steps=4 enter='bounceInRight' leave='bounceOutLeft')
      h3 Rare Event
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if="step>=2") Something
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if="step>=3") Examples of such rare interactions would include Coherent Elastic Neutrino Nucleus S
          |cattering, Dark matter Interactions, neutrino less double beta decay.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if="step>=4") Some examples of experiments that search for rare events are:
          ul
            li <b>MINER</b> (CEvNS, Sterile Neutrino)
            li <b>SuperCDMS</b>. (Dark matter)

    slide(:steps=5, enter='bounceInRight' leave='bounceOutLeft').MINER
      h3
        img(src="./assets/niser_logo.jpg").niser_logo
        | MINER
        img(src="./assets/texas_A_and_M.jpg").texas_anm_logo
      .container-fluid
        .row
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            p(v-if="step >= 2") Mitchell Institute Neutrino Expirement at Reactor
          eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
            p(v-if="step >= 3") Located at Nuclear Science Center in Texas A & M University
          .col-6
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if="step >= 4") Searching for Coherent Elastic neutrino Nucleus Scattering (CEvNS)
            eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
              p(v-if="step >= 5") By placing detectors a few meters from the reactor core.
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(v-if="step >= 4" src="./assets/CEvNS.jpg" alt="CEvNS")

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
          p Neutrino-Nucleus Collision

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
                li(v-if='step>= 8') Creates a Neutrion Flux of 3.73 x 10<sup>11</sup>neutrino/cm<sup>2</sup>/s
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(v-if='step >= 4' alt="Uranium Decay Chain" src="./assets/uranium_decay_chain.png")

    slide(:steps=8, enter='bounceInRight')
      h3 The signal
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        img(src="./assets/CEvNS.jpg" v-if="step >= 3").cevns
      .center
        eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
          p(v-if='step >= 2') Caused by CEvNS (Coherent Elastic Neutrino Nucleus Scattering)
      .container-fluid
        .row
          eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
            .col-3(v-if='step >= 3')
              Neutrino(:energy="1")
          eg-transition(enter='bounceInRight' leave='bounceOutRight')
            .col-7(v-if='step >= 3').half-wide
              p.coherent Coherent: Collision with the nucleus as a whole. Requires the neutrino to have energy order of 50MeV.

        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if='step >= 4') Elastic implies conservation of Energy and Momentum.
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if='step >= 5') These interactions cause:
        ul
          eg-transition(enter='fadeIn' leave='fadeOut')
            li(v-if='step>=6') Neutrino Scattering
          eg-transition(enter='fadeIn' leave='fadeOut')
            li(v-if='step>=7') Nuclear Recoil (Recorded in the form in deposited energy) (THE SIGNAL)
        eg-transition(enter='bounceInRight' leave='bounceOutRight')
          p(v-if="step >=8") Expecting an Event rate of 0.488/day

    slide(:steps=1, enter='bounceInRight')
      h3 Background
      .center
        p Anything other than neutrinos that can deposit energy in the detector is background.
      table
        tr
          th Background
          th Source
        tr
          td Electron
          td Reactor + Cosmogenic
        tr
          td Muons
          td Reactor + Cosmogenic
        tr
          td Gamma
          td Reactor + Cosmogenic

    slide(:steps=8 enter='bounceInRight')
      h3 Problem
      eg-transition(enter='bounceInRight' leave='BounceOutRight')
        p(v-if='step >=2') <b>Signal vs Background</b>
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p something
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p(v-if='step>=5') Background needs to be
      ul
        eg-transition(enter='bounceInRight' leave='bounceInRight')
          li(v-if='step>=6') Understood
        eg-transition(enter='bounceInRight' leave='bounceInRight')
          li(v-if='step>=7') Reduced
        eg-transition(enter='bounceInRight' leave='bounceInRight')
          li(v-if='step>=8') Rejected

    slide(:steps=3 enter='bounceInRight')
      h3 Understanding the background
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p(v-if='step>=2') Source of background and their flux.
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p(v-if='step>=3') **Table with the flux for all backgrounds**

    slide(:steps=5 enter='bounceInRight')
      h3 Reducing the background
      p.small What I wanna work on...
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p(v-if='step>=2') To stop the backgrounds from reaching the detector:
      .container-fluid
        .row
          .col-6
            eg-transition(enter='bounceInRight' leave='bounceInRight')
              p(v-if='step>=3') Shielding Material
            eg-transition(enter='bounceInRight' leave='bounceInRight')
              p(v-if='step>=4') Shielding Geometry
            eg-transition(enter='bounceInRight' leave='bounceInRight')
              p(v-if='step>=5') Detector Geometry and Position
          .col-6
            eg-transition(enter='fadeIn' leave='fadeOut')
              img(src="./assets/experiment_site.png" v-if='step>=3' style='transform:scale(2); margin-left: 40%;margin-top: 20%;')

    slide(:steps=2 enter='bounceInRight')
      h3 Rejecting Background
      eg-transition(enter='bounceInRight' leave='bounceInRight')
        p(v-if='step>=2') Finally, of the background that reaches the detector,
          |
          |we want to "somehow" differentiate it's signal from the signal of CEvNS

    slide(:steps=5 enter='bounceInRight' leave='bounceOutLeft')
      h3 Simulation
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=2') We use <b>GEANT4</b> as the framework for Simulation.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=2') Geant4 is a toolkit for the simulation of the passage of particles through
          | matter. Its areas of application include high energy, nuclear and accelerator physics,
          |as well as studies in medical and space science.
      eg-transition(enter='bounceInRight' leave='bounceOutRight')
        p(v-if='step>=3') I was able to simulate the following geometry:
      .container-fluid
        .row
          .col-4
            eg-transition(enter='bounceInRight' leave='bounceOutRight')
              img(src="./assets/G4detector.png" alt="Image of geometry" v-if='step>=3')
          .col-8
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
                  td 0
                  td (1/2)"
                  td 4mm
                tr
                  td Cylinder
                  td Silicon
                  td (1/2)"
                  td (3/2)"
                  td 1"

    slide(enter='fadeIn' :steps=2)
      h3 Thank you !
      p Credits and Acknowledgements
      end-credits
</template>

<script>
import eagle from 'eagle.js'

export default {
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

<style lang='scss'>
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
    width: 110%;
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
  .text-left {
    text-align: left;
  }
  .coherent {
    line-height: 1.1;
    margin-bottom: -0.36px;
    margin-top: 15.64px;
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
}
</style>
