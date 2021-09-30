<template>
  <header>
    <h1><a href="/">Boolflix</a></h1>
    <div id="input_cont">
      <input type="text" v-model="inputTxt" placeholder="Search here.." @keyup.enter="$emit('searchResults', inputTxt)">
      <button class="fas fa-search" @click="$emit('searchResults', inputTxt)"></button>
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

header {
  background-color: #000000;
  width: 100%;
  height: 70px;
  padding: 0 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;

  h1 a {
    text-decoration: none;
    color: red;
    font-size: 42px;
  }

  #input_cont{
    height: 35px;
    display: flex;

    input {
      background-color: #111111;
      color: #FFFFFF;
      outline: none;
      border: none;
      // border-radius: 10px ;
      padding-left: 10px;

      &:active, &:focus-visible {
        background-color: #555555;  
        border-bottom: 1px solid #FFFFFF ;
      }

      &::placeholder{
        color: #999999;
      }
    }

    button {
      border: none;
      color: #FFFFFF;
      background: none;
      padding: 10px;

      font-size: 20px;
    }
  }

}

</style>
