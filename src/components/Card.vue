<template>
  <li>
    <div class="item_title">{{item.title ? item.title : item.name}}</div>
    <div class="item_real_name">({{item.original_title ? item.original_title : item. original_name}})</div>
    <div :class="'flag-icon flag-icon-'+ (item.original_language == 'en' ? 'us': ' not_here' )"></div>
    <div class="item_vote">{{item.vote_average}}</div>
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
      
    }
}
</script>

<style scoped lang="scss">


</style>