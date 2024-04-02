<template>
  <div id="app">
    <div>
      <h1>Conditional Rendering</h1>
      <h2 v-if="num === 0">The Number is Zero</h2>
      <h2 v-else-if="num < 0">The Number is Negative</h2>
      <h2 v-else-if="num > 0">The Number is Positive</h2>
      <h2 v-else>Not a Number</h2>
    </div>
    <div v-if="display">
      <h2>Ashok</h2>
      <h2>Amara</h2>
    </div>
    <div>
      <h2 v-show="showElement">Using v-show</h2>
      <h2 v-if="showElement">Using v-if</h2>
    </div>
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
      <form @submit="submitForm">
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
        <br/><br/>
        <div>
          <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no"/>
          <label for="remoteWork">Open to work Remote?</label>
        </div>
        <br/><br/>
        <div>
          <label>Skill Set</label><br/>
          <input type="checkbox" id="html" value="html" v-model="formValues.skillSet"/>
          <label for="remoteWork">HTML</label>
          <input type="checkbox" id="css" value="css" v-model="formValues.skillSet"/>
          <label for="css">CSS</label>
          <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet"/>
          <label for="javascript">Javascript</label>
        </div>
        <div>
          <label>Years of Experience</label>
          <input type="radio" value="0-2" id="0-2" v-model="formValues.yearsOfExperience"/>
          <label for="0-2">0 - 2</label>
          <input type="radio" value="3-5" id="3-5" v-model="formValues.yearsOfExperience"/>
          <label for="3-5">3 - 5</label>
          <input type="radio" value="6-8" id="6-8" v-model="formValues.yearsOfExperience"/>
          <label for="6-8">6 - 8</label>
          <input type="radio" value="8+" id="8+" v-model="formValues.yearsOfExperience"/>
          <label for="8+">8+</label>
        </div>
        <div>
          <button class="submit">Submit</button>
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
      jobLocation:[],
      remoteWork:"no",
      skillSet:[],
      yearsOfExperience:''
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
    },
    submitForm(event){
      event.preventDefault();
      
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
.name{width:300px;height: 30px;}
textarea{width: 300px;height:70px}
select{width:300px;height: 50px;}
</style>
