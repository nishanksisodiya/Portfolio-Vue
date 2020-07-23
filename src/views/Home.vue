<template>
  <div class="home" @wheel="animate">
    <div class="left">
      <p class="name-title mask">Nishank Singh<br>Sisodiya</p>
    </div>
    <div class="right">
      <p class="name-title">Nishank Singh<br>Sisodiya</p>
    </div>
    <div class="scroll-down-icon">
      <v-icon light large class="scroll-down-icon">mdi-chevron-double-down</v-icon>
    </div>
  </div>
</template>

<script>
import anime from 'animejs'
import Intro from './Intro'

export default {
  name: 'Home',
  methods: {
    animate (event) {
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
          duration: 1500
        }).finished.then(() => {
          this.$router.push(Intro)
        })
      }
    }
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

  .scroll-down-icon {
    position: absolute;
    width: 100%;
    bottom: 10px;
    display: flex;
    justify-content: center;
    align-content: center;
  }
</style>
