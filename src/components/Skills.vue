<template>
  <v-container class="fill-height d-flex align-content-center justify-space-around">
    <v-row justify="center">
      <v-card-title>My Skills..</v-card-title>
    </v-row>
    <v-row justify="center">
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/javascript.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">JavaScript</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/vue.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">Vue JS</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/vuetify.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">Vuetify<br><span style="font-size: smaller" class="font-weight-light">Framework for vue</span>
        </v-card-text>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/python.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">Python</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/html5.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">HTML5</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/css3.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">CSS3</v-card-text>
      </v-col>
    </v-row>
    <v-row justify="center">
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/cpp.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">C++</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/adobecc.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">Adobe CC</v-card-text>
      </v-col>
      <v-col cols="6" md="4">
        <div class="d-flex justify-center">
          <v-avatar tile :size="$vuetify.breakpoint.mdAndUp ? 54:32">
            <v-img contain src='~@/assets/icons/git.svg'/>
          </v-avatar>
        </div>
        <v-card-text class="text-center">Git</v-card-text>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Skills',
  data: () => ({
    //
  })
}
</script>
