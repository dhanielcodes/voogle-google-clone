<template>
  <div class="hello">
    
  </div>
</template>

<script>
import  { } from 'vue'
import axios from 'axios'
export default {
  setup() {

    axios.get('https://en.wikipedia.org/w/api.php?action=query&generator=search&gsrsearch=food&gsrlimit=40&prop=pageimages|extracts&exchars=30&exintro&explaintext&exlimit=max&format=json&origin=*')
    .then(res => {
      console.log(res)
    })


    return{ }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
