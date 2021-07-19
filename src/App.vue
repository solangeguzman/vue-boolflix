<template>
  <div id="app">
    <Header />
    <Main :albumsMovie="filteredAlbumsArray"/>
  <!-- andava nel Main @search="searchcardisk" -->
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
      inputSearch:''

    };
  },
  created() {
    axios.get("https://api.themoviedb.org/3/search/movie?api_key=31eaab22661753a4564e4f0c10e72642&query=ritorno+al+futuro").then((response) => {
      this.albumsMovie = response.data.response;
      this.searchMovie('')
    })
  },
  computed:{
    filteredAlbumsArray(){
       return this.albumsMovie.filter((item) =>{
       return item.title.includes(this.inputSearch);
       })
    }
  },
  methods: {
    
    searchMovie(searchString){
      this.inputSearch = searchString
    },
    searchMovie(searchString){
     this.filteredAlbumsArray = this.albumsArray.filter((item) =>{
      return item.title.includes(searchString);
    })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>