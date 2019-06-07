<template>
  <div>
    <searchjokes v-on:search-text="searchText"/>
    <br/>
    <joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke"></joke>
  </div>
</template>

<script>
import axios from 'axios';
import searchjokes from '../../components/searchjokes.vue';
import joke from '../../components/joke.vue';
export default {
  components:{
      joke,
      searchjokes
  },
  data(){
    return {
      jokes:[]
    }
  },
  async created(){
    const config = {
      headers:{
        'Accept':'application/json'
      }
    }

try{
  const res = await axios.get('https://icanhazdadjoke.com/search',config)
  this.jokes = res.data.results;
}catch(err){
  console.log(err)
}
    
  },
  methods:{
    async searchText(text){
      const config = {
      headers:{
        'Accept':'application/json'
      }
    }

try{
  const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`,config)
  this.jokes = res.data.results;
}catch(err){
  console.log(err)
}
    }
  },
  head() {
    return {
      title: "Dad Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for dad jokes"
        }
      ]
    };
  }
};
</script>

<style>
</style>
