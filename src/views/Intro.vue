<template>
  <v-main class="home">
    <v-container class="fill-height d-flex align-content-center justify-space-around" @wheel="navigate">
      <v-row justify="center">
        <v-card elevation="0" color="transparent">
          <v-card-title class="justify-center" :style="{fontSize: '42px'}">About Me..</v-card-title>
          <v-card-subtitle>Programmer | Designer | UI Nerd | Gamer</v-card-subtitle>
        </v-card>
      </v-row>
      <v-row justify="center">
        <v-col cols="10">
          <p align="center">
            I'm a programmer with a passion for web designing. I love solving problems and increasing efficiency of the code
            <br>
            I use VueJS to create slick and responsive Web UIs.
          </p>
        </v-col>
      </v-row>
      <v-row class="mt-7" justify="center">
        <v-col lg="4" md="6" sm="12" cols="12" style="border-right: 1px solid white">
          <v-card elevation="0" color="transparent">
            <div class="d-flex justify-center">
              <v-avatar tile size="54">
                <v-img contain src='~@/assets/icons/infosys.svg'/>
              </v-avatar>
            </div>
            <v-card-title class="d-flex justify-center">Infosys Certified</v-card-title>
            <v-card-text class="text-center">
              I'm a Infosys Certified Software Programmer <br>
              You can verify my certificate <a target="_blank"  class="text-decoration-none" :href="infosysCert">here</a>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col lg="4" md="6" sm="12" cols="12">
          <v-card elevation="0" color="transparent">
            <div class="d-flex justify-center">
              <v-avatar tile size="54">
                <v-img contain src='~@/assets/icons/sih.svg'/>
              </v-avatar>
            </div>
            <v-card-title class="d-flex justify-center">SIH 2019</v-card-title>
            <v-card-text class="text-center">
              Finalist in Smart India Hackthon 2019
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
      <div class="scroll-down-icon">
        <v-icon dark>mdi-chevron-double-down</v-icon>
      </div>
    </v-container>
  </v-main>
</template>

<script>
import anime from 'animejs'
import Skills from './Skills'
import Home from './Home'

export default {
  name: 'Intro',
  data: () => ({
    infosysCert: 'https://infytq.infosys.com/public/lex_auth_012770921691734016639/ad121252-0f91-4883-9868-3dd111e633ed.pdf'
  }),
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
        this.$router.push(Home)
      } else {
        this.$router.push(Skills)
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
