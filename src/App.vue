<template>
  <h1>Weather Application</h1>
  <Search @weather="weather_details" />
  <Data v-bind:details="w_det" />
</template>

<script>

import Data from './components/Data'
import Search from './components/Search'


export default {
  name: 'App',
  components: {
    Search,
    Data
  },
  data(){
    return{
      w_det: {}
    }
  },
  methods:{
    weather_details(det){
      console.log("hhhhhh")
      console.log(det)
      console.log("khwdhdkkhhkwdkh")
      this.w_det=det
    }
  }
}
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@500&display=swap');
    h1{
        text-align: center;
        font-size: 200%;
        margin: 1% 14% 1% 14%;
        padding: 2%;
        font-family: 'Montserrat', sans-serif;;
    }
</style>
