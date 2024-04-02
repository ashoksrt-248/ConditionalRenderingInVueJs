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
    <hr></hr>
    <h1>Event Handling in VueJS</h1>
    <div>
      <h1>{{ count }}</h1>
      <button @click="increment(1)">Increment 1</button>
      <button @click="increment(5)">Increment 5</button>
      <button @click="decrement(1)">Decrement 1</button>
      <button @click="decrement(5)">Decrement 5</button>
    </div>
    <div>
      <h1>{{ name }}</h1>
      <button @click="changeName()">Change Name</button>
      <button @click="changeName2()">Change Name</button>
    </div>
  </div>
  
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      num:"hello",
      display:true,
      showElement:true,
      count:0,
      name:'Ashok'
      
    }
  },
  methods:{
    increment(num){
      this.count += num
    },
    decrement(num){
      this.count -= num
    },
    changeName(){
      this.name = 'DeVansh'
    },
    changeName2(){
      this.name = 'VeDansh'
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
  background-color: slategrey;
}
</style>
