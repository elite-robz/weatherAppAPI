<template>
  <form @click.prevent="handleSubmit">
      <label>City or Zip Code:</label>
      <input type="text" required v-model="searchTerm">
      <div class="error" v-if="info.message">{{info.message}}</div>
      <button>Search</button>
      
  </form>
  <div v-if="!info.message">
  <div v-if="info" class="container">
  <div class="info">City: {{info.name}}</div>
  <div class="info">Temp: °{{info.main.temp.toFixed(0)}}</div>
  <div class="info">Feels like: °{{info.main.feels_like.toFixed(0)}}</div>
  </div>
  </div>
  
</template>

<script>
import { ref } from 'vue'
import getWeather from '../composable/getWeather'
export default {
setup(){
    const searchTerm = ref('')
    const info = ref('')
    const handleSubmit = async() => {
        if(searchTerm.value){
        info.value = await getWeather(searchTerm.value)
        searchTerm.value = ''
    }
    }
    return {handleSubmit,searchTerm,info}
}
}
</script>

<style scoped>
label{
    font-size: 25px;
}
h2{
    font-size: 40px;
    font-style: italic;
}
.info{
    margin: auto;
}
</style>