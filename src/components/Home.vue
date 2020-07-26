<template>
  <div class="home">
    <div class="left">
      <p class="name-title mask mb-n16">
        Nishank Singh<br>Sisodiya<span class="brxsmall"/>
        <i class="mt-n16" style="font-size: 2vmin">A CS Graduate with a passion for UI Designing</i>
      </p>
    </div>
    <div class="right">
      <p class="name-title mb-n16">
        Nishank Singh<br>Sisodiya<span class="brxsmall"/>
        <span class="mt-n16 font-weight-light"
              style="font-size: 2vmin">A CS Graduate with a passion for UI Designing</span>
      </p>
    </div>
    <div class="scroll-down-icon">
      <v-icon light>mdi-chevron-double-down</v-icon>
    </div>
    <div class="page-container" id="achievements">
      <Intro/>
    </div>
    <div class="page-container" id="skills">
      <Skills/>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap'
import MotionPathPlugin from 'gsap/MotionPathPlugin'
import ScrollTrigger from 'gsap/ScrollTrigger'
import Skills from './Skills'
import Intro from './Intro'

gsap.registerPlugin(MotionPathPlugin)
gsap.registerPlugin(ScrollTrigger)

export default {
  name: 'Home',
  components: { Intro, Skills },
  mounted () {
    gsap.timeline({
      scrollTrigger: {
        trigger: '.home',
        start: 'top top',
        end: 'bottom+=1000 top',
        pin: true,
        scrub: 0.5,
        markers: true
      },
      defaults: {
        duration: 3
      }
    })
      // Main home animation
      .to(['.left'], {
        clipPath: 'polygon(0 0, 100% 0, 100% 100%, 0 100%)',
        ease: 'power1.out'
      }, 'scene')
      // Name scaling animation
      .to(['.name-title'], {
        scale: 0,
        ease: 'power1.out'
      }, 'scene')
      // Achievements reveal animation
      .from(document.getElementById('achievements').querySelectorAll('.row'), {
        motionPath: {
          path: [
            {
              x: 0,
              y: 100
            }
          ]
        },
        autoAlpha: 0,
        stagger: 0.2,
        ease: 'power3.in'
      }, '-=3')
      // Hide achievements animation
      .to(document.getElementById('achievements').querySelectorAll('.row'), {
        motionPath: {
          path: [
            {
              x: 0,
              y: -100
            }
          ]
        },
        autoAlpha: 0,
        stagger: 0.2,
        ease: 'power3.in'
      }, '+=3')
      // Hide achievements div after animation
      .to(document.getElementById('achievements'), {
        autoAlpha: 0
      })
      // Skills reveal animation
      .from(document.getElementById('skills').querySelectorAll('.row'), {
        motionPath: {
          path: [
            {
              x: 0,
              y: 100
            }
          ]
        },
        autoAlpha: 0,
        stagger: 0.2,
        ease: 'power3.in'
      }, '-=2')
  }
}
</script>

<style>
  .home {
    min-height: 100vh;
    display: flex;
  }

  .left, .right {
    min-height: 100%;
    display: flex;
    min-width: 100%;
    justify-content: center;
  }

  .left {
    background: #000000;
    position: absolute;
    top: 0;
    left: 0;
    clip-path: polygon(0 0, 100% 0, 100% 0, 0 100%);
    z-index: -1;
  }

  .right {
    background: #ffffff;
    clip-path: polygon(100% 0, 100% 100%, 0 100%);
    z-index: -2;
  }

  .name-title {
    align-self: center;
    font-size: 5vmax;
    font-weight: normal;
    line-height: 1em;
    text-align: center;
    color: black;
  }

  .mask {
    background: url("~@/assets/img/bg.jpg");
    background-size: cover;
    filter: invert();
    background-clip: text;
    color: transparent;
  }

  .brxsmall {
    display: block;
    margin-bottom: -.5em;
  }
  .page-container {
    position: absolute;
    display: flex;
    align-items: center;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
  }
  #achievements {
    z-index: 3;
  }
  #skills {
    z-index: 2;
  }
</style>
