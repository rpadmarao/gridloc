/* global google */
<template>
  <div>
    <SearchBar @search="search"></SearchBar>
    <div class='google-map' :id="mapName"></div>
  </div>
</template>

<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyBo3L6AEYoMI1ot6dlyS8nVxyEgzQ0nOLc" ></script>
<script>
import SearchBar from './SearchBar.vue'

export default {
  name: 'google-map',
  props: ['name'],
  components: {
    'SearchBar': SearchBar
  },
  data: function () {
    return {
      mapName: this.name + '-map'
    }
  },
  methods: {
    search: (value) => {
      console.log(value) // value is the text in the search bar
    }
  },
  /*eslint-disable*/
  mounted: function () {
    const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(41.997498, -93.632537)
    }

    const map = new google.maps.Map(element, options)

    map.data.addListener('click', function(event){

    });
  }
  /*eslint-enable*/
}
</script>

<style scoped>
.google-map {
  position: absolute;
  top: 0px;
  left: 0px;
  right: 0px;
  bottom: 0px;
  margin: 0 auto;
  background: gray;
  z-index: 0;
}
</style>
