<template>
  <div id="app">
    <Hello></Hello>
    <LikedPics></LikedPics>
  </div>
</template>

<script>
import Hello from './components/Hello';
import LikedPics from './components/LikedPics';

export default {
  name: 'app',
  components: {
    Hello,
    LikedPics
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
  margin-top: 60px;
}
</style>
