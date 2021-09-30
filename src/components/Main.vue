<template>
  <main>
    <section class="movies">
        <h2>Films</h2>
        <ul class="cards">
          <Card v-for="card in movieCards" :key="card.id" :item="card"/>
        </ul>
    </section>  
    <section class="tvShows">
        <h2>Tv Shows</h2>
        <ul class="cards">
          <Card v-for="card in tvCards" :key="card.id" :item="card"/>
        </ul>
    </section>  
  </main>
</template>

<script>
import Card from './Card.vue'

export default {
    name: "Main",
    components: {
      Card
    },
    props: {
      movieCards: Array,
      tvCards: Array
    }
}
</script>

<style scoped lang="scss">

main {
    background-color: #333333;
    color: #FFFFFF;
    height: calc(100% - 70px);

  h2 {
    font-size: 32px;
    margin-left: 20px;
  }

  .cards{
    display: flex;

  flex-wrap: wrap;
  }
}

.movies, .tvShows {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
</style>