<template>
  <CityWeather />
</template>

<script>
import CityWeather from './components/CityWeather'

export default {
  name: 'App',
  components: {
    CityWeather,
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
