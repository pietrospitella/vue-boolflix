<template>
  <main>
    <section class="movies">
        <h2>Films</h2>
        <ul class="cards">
            <li v-for="(card, index) in movieCards" :key="index">
              {{card.title}}
              <br>
              ({{card.original_title}})
              <br>
              {{card.original_language}}
              <br>
              {{card.vote_average}}
              </li>
        </ul>
    </section>  
  </main>
</template>

<script>
export default {
    name: "Main",
    props: ["movieCards"]
}
</script>

<style scoped lang="scss">

</style>