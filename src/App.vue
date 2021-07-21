<template>
  <div id="app">
    <Header @search="searchMovie" @click="button" />
    <Main :albumsMovie="albumsMovie"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      albumsMovie: [],

    };
  },
  created() {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=31eaab22661753a4564e4f0c10e72642&").then((results) => {
      this.albumsMovie = results.data.results;
      this.searchString="";
    });
  },
  methods:{
    searchMovie(searchString){
      if(searchString.length == 0){
         axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=31eaab22661753a4564e4f0c10e72642&`).then((results) =>{
         this.albumsMovie=results.data.results;
       });
      }else{
        axios.get(`https://api.themoviedb.org/3/search/multi/?api_key=31eaab22661753a4564e4f0c10e72642&query=${searchString}`).then((results)=>{
          this.albumsMovie= results.data.results;
        });
      }
       
    },
  },
}
</script>

<style lang="scss">
#app {
background-color: rgba(0, 0, 0, 0.726);

}
</style>