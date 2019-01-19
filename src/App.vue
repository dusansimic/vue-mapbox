<template>
  <div id="app">
    <Mapbox
      access-token="pk.eyJ1IjoiZHVzYW5zaW1pYyIsImEiOiJjamp1Zm95ZngxNmJ4M3BtaDV2eXM5dm12In0.t4lx-WhB2TDMI-YTdVZqyg"
      :map-options="{
        style: 'mapbox://styles/mapbox/streets-v10',
        center: [19.8532383, 45.2413324],
        zoom: 15
      }"
      :geolocate-control="{
        show: true,
        position: 'top-left'
      }"
      :scale-control="{
        show: true,
        position: 'top-left'
      }"
      :fullscreen-control="{
        show: true,
        position: 'top-left'
      }"
      :markers="[
        {
          options: {
            color: '#ff0000'
          },
          location: [19.849888, 45.244981],
          popup: {
            html: '<h3>IdeaLab</h3><a href=&quot;/application/sodaq-demo/device/sodaq-maker-2&quot;>path to idealab</a>'
          }
        },
        {
          location: [19.8498394, 45.248725]
        }
      ]"
    ></Mapbox>
  </div>
</template>

<script>
import Mapbox from './components/Mapbox'

export default {
  name: 'app',
  components: {
    Mapbox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#map {
  text-align: left;
  width: 100%;
  height: 100vh;
}
</style>
