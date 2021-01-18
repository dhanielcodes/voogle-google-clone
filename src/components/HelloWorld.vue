<template>
  <div class="hello">
    <form @submit.prevent="searchFunction">
      <input v-model="search" type="text" name="" id="">
    </form>
    <h3>Results for <span>"{{search}}"</span></h3>
    <div class="f" v-for="(item, index) in data" :key="index">
      {{item.title}}<br>
      <a target="_blank" :href="`https://en.wikipedia.org/?curid=${item.pageid}`">{{'https://en.wikipedia.org/?curid=' + item.pageid}}</a><br>
      {{item.snippet}}
      <hr />
    </div>
  </div>
</template>

<script>
import  { ref } from 'vue'
import axios from 'axios'
export default {
  setup() {

    const data = ref([])
    const search = ref('')
    function searchFunction(){
      axios.get('https://en.wikipedia.org/w/api.php?action=query&list=search&prop=info&inprop=url&utf8=&format=json&origin=*&srlimit=20&srsearch=' + search.value)
      .then(res => {
        console.log(res.data.query.search)
        data.value = res.data.query.search
      })
    }


    return{ data, search, searchFunction }
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
