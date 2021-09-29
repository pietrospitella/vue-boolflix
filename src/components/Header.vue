<template>
  <header>
    <h1><a href="/">Boolflix</a></h1>
    <div>
      <input type="text" v-model="inputTxt" placeholder="Cerca il tuo film" @keyup.enter="$emit('searchResults', inputTxt)">
      <button @click="$emit('searchResults', inputTxt)">Cerca</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputTxt: ''
    }
  },
  props: {
    
  }
}
</script>


<style scoped lang="scss">

</style>
