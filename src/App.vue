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
      .then(res => (this.info = res.data))
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

      <p v-show="info != null">{{info.main.temp}} Grade</p>
    </div>
  </div>
</template>



<style scoped>
.wrapper{
  width: 300px;
  height: 400px;
  border-radius: 50px;
  background: #66d6e1;

  text-align: center;
  
}

.header_app{
  text-align: center;
  padding-top: 10px;
}

.input_app{
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 15px;
  
  margin-top: 35px;
}

.input_app input{
  background: transparent;
  padding: 5px 8px;
  border: 0;
  border-bottom: 1px black solid;

  color: white;
  font-size: 14px;
  outline: none;
}

.input_app input:focus{
  
  border-bottom: 2px rgb(161, 0, 0) solid;

}

.input_app button{
  padding: 10px 13px;
  border: 0;
  background-color: #ffffff;
  border-radius: 50px;
  cursor: pointer;

}

.result_app{
  text-align: center;
  margin-top: 35px;
}

.error_app{
  margin-top: 5px;
  color: red;
}
</style>