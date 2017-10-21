<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script src='https://maps.googleapis.com/maps/api/js?key=AIzaSyBo3L6AEYoMI1ot6dlyS8nVxyEgzQ0nOLc' ></script>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*
  margin-top: 0px;
  margin-right: 0px;
  margin-left: 0px;
  margin-bottom: 0px;
  padding-top: 0px;
  padding-right: 0px;
  padding-left: 0px;
  padding-bottom: 0px;
  */
}
</style>
