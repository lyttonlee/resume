<template>
  <div id="app">
    <Resume/>
  </div>
</template>

<script>
import Resume from './components/resume'

export default {
  name: 'App',
  components: {
    Resume
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
</style>
