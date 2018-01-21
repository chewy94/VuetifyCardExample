<template>
  <v-app>
    <v-content>
      <v-container fluid class="bgcolor-2">
        <v-layout row wrap justify-center>
          <v-flex xs12 sm4 md2>
            <v-card class="bgcolor">
              <v-card-title class="headline pb-0">San Francisco</v-card-title>
              <v-subheader>Mon, 12:30 PM, Mostly sunny</v-subheader>
              <v-layout row wrap align-center text-xs-center>
                <v-flex xs6>
                  <v-card-text class="display-3">23&deg;C</v-card-text>
                </v-flex>
                <v-flex xs6>
                  <img src="https://image.ibb.co/hsTWib/Screen_Shot_2018_01_18_at_9_19_23_PM.png" alt="Sunny image">
                </v-flex>
              </v-layout>
              <v-card-text>
                <v-icon>send</v-icon>
                <span class="pl-3">23 km/h</span>
              </v-card-text>
              <v-card-text>
                <v-icon>cloud_download</v-icon>
                <span class="pl-3">48%</span>
              </v-card-text>
              <v-slider class="pl-3"
                        v-model="time" 
                        step="3" 
                        ticks
                        :max="24"
                        thumb-label
              ></v-slider>
              <v-list class="bgcolor">
                <v-list-tile v-for="item in forecast" :key="item.day">
                  <v-layout row wrap>
                    <v-flex xs6>
                      <v-list-tile-title>{{ item.day }}</v-list-tile-title>
                    </v-flex>
                    <v-flex xs6>
                      <v-layout row wrap>
                        <v-flex xs6 class="text-xs-left">
                          <v-icon>{{ item.icon }}</v-icon>
                        </v-flex>
                        <v-flex xs6 class="">
                          <div>{{ item.temp }}</div>
                        </v-flex>
                      </v-layout>
                    </v-flex>
                  </v-layout>
                </v-list-tile>
              </v-list>
              <v-divider></v-divider>
              <v-btn flat>Full Report</v-btn>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        time: 0,
        forecast: [
          { day: 'Tuesday', icon: 'wb_sunny', temp: '24\xB0/12\xB0' },
          { day: 'Wednesday', icon: 'wb_sunny', temp: '22\xB0/14\xB0' },
          { day: 'Thursday', icon: 'cloud', temp: '25\xB0/15\xB0' },
        ]
      }
    }
  }
</script>

<style scoped>
.bgcolor {
  background-color: #F9F9F9 !important;
}
</style>
