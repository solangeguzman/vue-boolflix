<template>
  <div id="app">
    <Header @search="searchMovie" />
    <Main :albumsMovie="albumsMovie"/>
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Main from './components/Main.vue';
export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data() {
    return {
      albumsMovie: [],
    //   moviesFiltered: [],

    };
  },
  created() {
    axios.get("https://api.themoviedb.org/3/movie/popular?api_key=31eaab22661753a4564e4f0c10e72642&query=ritorno+al+futuro").then((results) => {
      this.albumsMovie = results.data.results;
    });
  },
  methods:{
    searchMovie(searchString){
        axios.get(`https://api.themoviedb.org/3/movie/popular?api_key=31eaab22661753a4564e4f0c10e72642&query=`+ searchString).then((results) =>{
        this.albumsMovie=results.data.results;
        // this.moviesFiltered= results.data.results;
       });
    },
  },
}
</script>

<style lang="scss">
#app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
  color: #2c3e50;
}
</style>