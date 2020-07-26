<template>
  <v-app dark>
    <v-main>
      <div class="progresser-container">
        <v-progress-circular
          class="progresser"
          :rotate="-90"
          :size="50"
          :width="3"
          :value="scrollPer"
          color="white"
        />
      </div>
      <home/>
    </v-main>
  </v-app>
</template>

<script>
import Home from './components/Home'

export default {
  name: 'App',
  components: { Home },
  data: () => ({
    scrollPer: 0
  }),
  methods: {
    scrollPerCalc () {
      const winScroll = document.body.scrollTop || document.documentElement.scrollTop
      const height = document.documentElement.scrollHeight - document.documentElement.clientHeight
      this.scrollPer = (winScroll / height) * 100
    }
  },
  mounted () {
    document.addEventListener('scroll', this.scrollPerCalc)
  }
}
</script>

<style>
  .progresser-container {
    position: fixed;
    margin-top: 20px;
    margin-left: 20px;
    top: 0;
    left: 0;
    display: flex;
    justify-content: left;
    align-items: center;
    z-index: 10;
  }
</style>
