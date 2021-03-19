<template>
  <div class="hello" v-if="result">
    <h1>{{ msg }}</h1>
    <p>Title: {{ result.results[0].name }}</p>
    
    
      
  
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: 'HelloWorld',
  data: () => ({
    result: null
  }),
  props: {
    msg: String
  },
  created() {
    axios.get("https://pokeapi.co/api/v2/pokemon/").then((result) => {
      this.result = result.data;
      console.log(result.data);
    })
  }
}
</script>
