<template>
  <div class="search-bar-container">
    <div class="search-bar">
      <form>
        <input type="text" name="search-field" placeholder="Search">
      </form>
      <img src="../assets/ic_search_black_24px.svg" class="search-icon" v-on:click="searchMap">
    </div>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    searchMap: function () {
      this.$emit('search')
    }
  }
}
</script>

<style>
  .search-bar-container {
    display: flex;
    align-items: center;
    justify-content: center;
    padding-top: 25px;
  }

  .search-bar {
    position: absolute;
    height: 50px;
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: white;
    z-index: 5;
    border-radius: 2px;
    box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
  }

  input[type="text"] {
    font-size: 20px;
    font-family: Roboto, sans-serif;
    height:1.5em;
    position: relative;
    display: flex;
    width: 380px;
    float: left;
    margin: 10px;
    border: none;
    border-right: 1px solid black;
  }
  .search-icon  {
    display: flex;
    align-items: center;
    padding: 5px;
  }
</style>
