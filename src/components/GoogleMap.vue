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
      mapName: this.name + '-map',
      map: null
    }
  },
  /*eslint-disable*/
  mounted: function () {
    console.log('Parent is mounted')
    const element = document.getElementById(this.mapName)
    const options = {
      zoom: 14,
      center: new google.maps.LatLng(41.997498, -93.632537)
    }

    this.map = new google.maps.Map(element, options)

    this.map.data.addListener('click', function(event) {
      this.map.setZoom(8);
      this.map.setCenter(marker.getPosition());
    });
  },
  methods: {
    search: (grid) => {
      console.log(this.map)
      var i = 0
      var l = []
      grid = grid.toUpperCase()
      while (i < 10) {
        l[i] = grid.charCodeAt(i++) - 65
      }
      l[2] += 17
      l[3] += 17
      l[6] += 17
      l[7] += 17
      var lng = (l[0] * 20 + l[2] * 2 + l[4] / 12 + l[6] / 120 + l[8] / 2880 - 180)
      var lat = (l[1] * 10 + l[3] + l[5] / 24 + l[7] / 240 + l[9] / 5760 - 90)
      console.log(lng)
      console.log(lat)
      var myLatlng = new google.maps.LatLng(lat,lng)
      var marker = new google.maps.Marker({
        position: myLatlng,
        map: this.map,
        title: 'Click to zoom'
      });
      console.log(marker.position, myLatlng)
    }
  }
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
