<template>
  <div class="home" @wheel="navigate">
    <div class="left">
      <p class="name-title mask mb-n16">
        Nishank Singh<br>Sisodiya<span class="brxsmall"/>
        <i class="mt-n16" style="font-size: 2vmin">A CS Graduate with a passion for UI Designing</i>
      </p>
    </div>
    <div class="right">
      <p class="name-title mb-n16">
        Nishank Singh<br>Sisodiya<span class="brxsmall"/>
        <i class="mt-n16" style="font-size: 2vmin">A CS Graduate with a passion for UI Designing</i>
      </p>
    </div>
    <div class="scroll-down-icon">
      <v-icon light>mdi-chevron-double-down</v-icon>
    </div>
    <div class="contact-me-btn">
      <v-btn text class="justify-end ml-5 mt-5" light href="mailto: nishanksisodiy@gmail.com" color="white">
        Contact me
      </v-btn>
    </div>
  </div>
</template>

<script>
import anime from 'animejs'
import Intro from './Intro'

export default {
  name: 'Home',
  methods: {
    navigate (event) {
      if (event.deltaY > 0) {
        anime({
          targets: '.name-title',
          opacity: 0,
          easing: 'easeInQuad',
          duration: 500
        })
        anime({
          targets: '.left',
          clipPath: 'polygon(0 0, 100% 0, 100% 100%, 0 100%)',
          easing: 'easeOutQuad',
          duration: 750
        }).finished.then(() => {
          this.$router.push(Intro)
        })
      }
    }
  },
  mounted () {
    anime({
      targets: '.scroll-down-icon',
      translateY: [-5, 0],
      duration: 1000,
      easing: 'linear',
      direction: 'alternate',
      loop: true
    })
  }
}
</script>

<style>
  .home {
    min-height: 100%;
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
    z-index: 1;
  }

  .right {
    background: #ffffff;
    clip-path: polygon(100% 0, 100% 100%, 0 100%);
    z-index: 0;
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

  .contact-me-btn {
    position: absolute;
    max-width: 100%;
    top: 0;
    display: flex;
    justify-content: center;
    align-content: center;
    z-index: 10;
  }

  .reveal {
    transition: transform .3s;
    width: 0;
    transform: scale(0);
  }

  .reveal-hover {
    width: auto;
    transform: scale(1);
  }
</style>
