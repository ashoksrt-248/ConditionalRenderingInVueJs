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
    <hr>
    <div>
      <form>
        <h1>Form Handling</h1>
        <pre>{{ JSON.stringify(formValues, null, 2) }}</pre>
        <div>
          <label for="name">Name</label><br/>
          <input type="text" id="name" v-model="formValues.name" />
        </div>
        <br/>
        <div>
          <label for="profile">Profile Summary</label><br/>
          <textarea id="profile" v-model="formValues.profileSummary" />
        </div>
        <div>
          <label for="country">Country</label><br/>
          <select id="country" v-model="formValues.country">
            <option value="">Select a Country</option>
            <option value="india">India</option>
            <option value="australia">Australia</option>
            <option value="newzeland">Newzeland</option>
            <option value="srilanka">Srilanka</option>
            <option value="america">America</option>
          </select>
        </div>
        <div>
          <label for="jobLocation">Job Location</label><br/>
          <select id="jobLocation" multiple v-model="formValues.jobLocation">
            <option value="">Select a Country</option>
            <option value="india">India</option>
            <option value="australia">Australia</option>
            <option value="newzeland">Newzeland</option>
            <option value="srilanka">Srilanka</option>
            <option value="america">America</option>
          </select>
        </div>
        <br/><br/><br/><br/>
        <div>

        </div>
      </form>
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
      name:'Ashok',
    formValues:{
      name:'',
      profileSummary:'',
      country:'',
      jobLocation:[]
    }
      
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
input{width:300px;height: 30px;}
textarea{width: 300px;height:70px}
select{width:300px;height: 50px;}
</style>
