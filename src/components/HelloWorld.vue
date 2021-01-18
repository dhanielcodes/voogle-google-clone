<template>
  <div class="hello">
    <form @submit.prevent="searchFunction">
      <input v-model="search" placeholder="Search Voogle" type="text" name="" id="">
    </form>
    <div class="searches" v-for="(item, index) in data" :key="index">
      <h2>{{item.title}}</h2>
      <a target="_blank" :href="`https://en.wikipedia.org/?curid=${item.pageid}`">{{'https://en.wikipedia.org/?curid=' + item.pageid}}</a>
      <p>{{item.snippet}}</p>
    </div>
    <div v-if="isLoading">Loading...</div>

  </div>
</template>

<script>
import  { ref, watch } from 'vue'
import axios from 'axios'
export default {
  setup() {

    const data = ref([])
    const search = ref('')
    const isLoading = ref(false)
    function searchFunction(){
      isLoading.value = true
      axios.get('https://en.wikipedia.org/w/api.php?action=query&list=search&prop=info&inprop=url&utf8=&format=json&origin=*&srlimit=20&srsearch=' + search.value)
      .then(res => {
        data.value = res.data.query.search
        isLoading.value = false
      })
    }

    watch(search, () => {
      searchFunction()
    })


    return{ data, search, searchFunction, isLoading }
  }
}
</script>

<style scoped>

form{
  width: 100%;
  margin-bottom: 50px
}
form input{
  width: 100%;
  padding: 20px;
  border-radius: 100px;
  border: none;
  background: #F3F3F3;
  outline: none;
}
::placeholder{
  color: #8CD0B2
}
a {
  color: #42b983;
}
.searches{
  padding: 20px;
  width: 100%;
  background: #35495E;
  color: white;
  border-radius: 40px;
  margin: 20px 0
}

</style>
