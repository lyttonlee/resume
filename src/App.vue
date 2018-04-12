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

<style lang="less">
#app {
  font-family: 'Hiragino Sans GB','WenQuanYi Micro Hei','Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', 'Microsoft YaHei', sans-serif;
  font-size: 15px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #12181f;
  @media screen and (max-width: 768px) {
    font-size: 8px;
  }
}
</style>
