<template>
  <li>
    <img :src="`https://image.tmdb.org/t/p/w92${item.poster_path}`" alt="">
    <div class="item_title">{{item.title ? item.title : item.name}}</div>
    <div class="item_real_name">({{item.original_title ? item.original_title : item. original_name}})</div>
    <div :class="'flag-icon flag-icon-'+ (item.original_language == 'en' ? 'us': ' not_here' )"></div>
    <div class="item_vote">
      <i v-for="n in 5" :key="n" class="fa-star" :class="(n <= starVote()) ? 'fas' : 'far'"></i>
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


</style>