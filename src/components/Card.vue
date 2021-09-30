<template>
  <li>
    <div class="card_front">
      <img v-if="item.poster_path" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
      <img v-else src="https://www.movieday.it/img/placeholder/Movie.png" alt="">
    </div>
    <div class="card_retro">
      <div class="item_title">{{item.title ? item.title : item.name}}</div>
      <div class="item_real_name">({{item.original_title ? item.original_title : item. original_name}})</div>
      <div :class="'flag-icon flag-icon-'+ (item.original_language == 'en' ? 'us': ' not_here' )"></div>
      <div class="item_vote">
        <i v-for="n in 5" :key="n" class="fa-star" :class="(n <= starVote()) ? 'fas' : 'far'"></i>
      </div>
      <div class="item_overview">{{item.overview}}</div>
    </div>
  </li>
</template>

<script>

export default {
    name: "Card",
    data(){
      return{
         
      }
    },
    props: {
      "item": Object
    },
    methods: {
      starVote(){
        return Math.ceil(this.item.vote_average / 2);
      }
    }
}
</script>

<style scoped lang="scss">

li {
  width: 340px;
  height: 513px;
  margin: 18px;
  list-style: none;
  position: relative;
  overflow: hidden;
  box-shadow: 0px 10px 10px 0px rgba($color: #000000, $alpha: 0.2);

  .card_front{
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card_retro{
    opacity: 0;
    position: absolute;
    top: 0;
    width: 100%;
    height: 100%;
    padding: 20px;
    background-color: rgba($color: #000000, $alpha: 0.4);

    &:hover{
      opacity: 1;
    }

    div {
      margin: 10px 0;
    }

    .item_title{
      font-size: 46px;
    }


  }
}

</style>