<template>
  <div class="home">
   <SearchBar />
  </div>
</template>

<script>

import SearchBar from '../components/SearchBar.vue'

export default {
  name: 'Home',
  components: {
    SearchBar
  }
}
</script>
<style>
.Home {
    text-align: center;
    padding: 20px 0;
   
  }
  /* form styles */
  form {
    width: 300px;
    margin: 20px auto;
  }
 label {
    display: block;
    margin: 20px 0 10px;
  }
  input {
    width: 100%;
    padding: 10px;
    border-radius: 20px;
    border: 1px solid #eee;
    outline: none;
    color: #999;
    margin: 10px auto;
  }
  span{
    font-weight: bold;
    text-decoration: underline;
    cursor: pointer;
  }
  button {
    margin: 20px auto;
  }
</style>