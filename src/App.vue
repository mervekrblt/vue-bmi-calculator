<script>
import BmiCalculator from '@/components/BmiCalculator'
import Header from '@/components/Header'

export default {
  name: 'App',
  components: {
    BmiCalculator,
    Header
  }
}
</script>

<template>
  <div id="app">
    <Header></Header>
    <bmi-calculator></bmi-calculator>
  </div>
</template>

<style>
body {
    margin: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/
}
</style>
