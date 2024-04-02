<template>
  <div id="app">
    <h2 v-if="num === 0">The Number is Zero</h2>
    <h2 v-else-if="num < 0">The Number is Negative</h2>
    <h2 v-else-if="num > 0">The Number is Positive</h2>
    <h2 v-else>Not a Number</h2>
    <div v-if="display">
      <h2>Ashok</h2>
      <h2>Amara</h2>
      <h1>Conditional Rendering</h1>
    </div>
    <h2 v-show="showElement">Using v-show</h2>
    <h2 v-if="showElement">Using v-if</h2>
    
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      num:"hello",
      display:true,
      showElement:true
    }
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
