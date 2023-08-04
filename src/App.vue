<script>
import axios from 'axios'
export default {
  data(){
    return{
      city: "",
      error: "",
      info: null,
    }
  },
  computed:{
    cityName(){
      return this.city == "" ?  "your city" : this.city
    }
  },
  methods: {
    getWeather(){
      if(this.city.trim().length < 2){
        this.error = "Too short input"
        return false
      }
      this.error = "";

      axios.get(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=9d41648851735f97a3652a461f6d2ae0`)
      .then(res => (this.info = res.data.main.temp))
    }
  },
}

</script>

<template lang="">
  <div class="wrapper">
    <div class="header_app">
      <h1>Web App</h1>
      <p>Weather in your City</p>
    </div>
    <div class="input_app">
      <input type="text" v-model="city" placeholder="Insert your City">
      <button type=submit v-if="city != ''" @click="getWeather()">Insert</button>
      <button disabled v-else>+</button>
    </div>

    <div class="error_app">
      <p class="error">{{ error }}</p>
    </div>

    <div class="result_app">
      <p>Weather in {{ cityName}} for today</p>

      <p v-show="this.info != null">{{ info }} Grade</p>
    </div>
  </div>
</template>

