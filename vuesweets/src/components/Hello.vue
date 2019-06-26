<template>
  <div class="hello">
    <button v-on:click="text = !text">Favorite</button>
    <p v-if="text">Is favorited? {{text}}</p>
    <p v-else="text">Is favorited? false</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
      text: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
