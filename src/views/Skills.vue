<template>
  <v-main class="home">
    <v-container class="fill-height d-flex align-content-center justify-space-around" @wheel="navigate">
      <v-row justify="center">
        <v-card-title>My Skills..</v-card-title>
      </v-row>
      <v-row justify="center">
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/javascript.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">JavaScript</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/vue.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">Vue JS</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/vuetify.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">Vuetify<br><span style="font-size: smaller" class="font-weight-light">Framework for vue</span></v-card-text>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/python.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">Python</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/html5.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">HTML5</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/css3.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">CSS3</v-card-text>
        </v-col>
      </v-row>
      <v-row justify="center">
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/cpp.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">C++</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/adobecc.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">Adobe CC</v-card-text>
        </v-col>
        <v-col cols="6" md="4">
          <div class="d-flex justify-center">
            <v-avatar tile size="54">
              <v-img contain src='~@/assets/icons/git.svg'/>
            </v-avatar>
          </div>
          <v-card-text class="text-center">Git</v-card-text>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<script>
import anime from 'animejs'
import Intro from './Intro'

export default {
  name: 'Skills',
  methods: {
    animateHome () {
      anime({
        targets: '.row',
        translateY: {
          value: [100, 0],
          easing: 'easeOutQuad',
          duration: 500
        },
        opacity: {
          value: [0, 1],
          duration: 750,
          easing: 'linear'
        },
        delay: anime.stagger(200)
      })
    },
    navigate (event) {
      if (event.deltaY < 0) {
        this.$router.push(Intro)
      }
    }
  },
  mounted () {
    this.animateHome()
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

<style scoped>
  .home {
    min-height: 100%;
    display: flex;
    background: black;
    justify-content: center;
  }
</style>
