<template>
  <div class="home">
    <v-container style="min-height: 100%; align-items: center">
      <v-row justify="center" align="center">
        <v-col cols="4">
          <h2 style=" width:100%; text-align: center">Who am I?</h2>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Intro'
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
