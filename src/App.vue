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
  background: url(https://images.unsplash.com/photo-1490818387583-1baba5e638af?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1531&q=80) no-repeat center fixed;
  background-size: cover;
  height: 100%;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

html,* {
  font-family: 'Ribeye Marrow', cursive;
  margin:0 0 ;
}



</style>
