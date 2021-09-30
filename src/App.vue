<template>
  <div id="app">
    <Header @searchResults="search"/>
    <Main :movieCards="movies" :tvCards="tvShows"/>
  </div>
</template>

<script>
import axios from 'axios'
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      apiUrl: "https://api.themoviedb.org/3/search/", 
      apiKey: "6c698a59662080dd823a50442fd8d368",
      movies: [],
      tvShows: []      
    }
  },
  methods: {
    getMovies(apiParams) {
      axios
        .get(this.apiUrl + 'movie', apiParams)
        .then(res => {
          this.movies = res.data.results;
        })
    },
    getTvShows(apiParams) {
      axios
        .get(this.apiUrl + 'tv', apiParams)
        .then(res => {
          this.tvShows = res.data.results;
        })
    },
    search(titleOfInterest){
      const paramsObj = {
        params : {
          api_key: this.apiKey,
          query: titleOfInterest
        }
      };
      this.getMovies(paramsObj);
      this.getTvShows(paramsObj);

    }
  }
}
</script>

<style lang="scss">

@import './styles/generals.scss';


</style>
