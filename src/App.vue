<template>

  <div>Hello {{name}}</div>
  <div v-html="name"></div> 
  <div v-html="alertCheck"></div>
  <div :id="name">{{name}}</div>
  <div class="Rajkumar">{{name}}</div>
  <button v-on:click="add($event)">{{Hell}}</button>
  <h1>{{count}}</h1>
  <button @mouseover="increment">increase</button>
    <button @click="count-=1">decrease</button>
    <div>
      {{formValue}}
    </div>
  <form @submit="testing">
    <div v-bind:style="{backgroundColor:'red'}"> 
      <label for="name">Name</label><br>
      <input type="text" id="name" placeholder="Enter the name" v-model="formValue.name">
    </div>
    <div>
      <label for="name">Select Country:</label><br>
      <select id="country" v-model="formValue.selectedValue">
        <option value="">Select a Country</option>
        <option value="india">India</option>
        <option value="america"> USE</option>
      </select>
    </div>
    <div>
      <label for="name">Select Country:</label><br>
      <select id="country"  multiple v-model="formValue.multipleValue">
        <option value="">Select a Country</option>
        <option value="india">India</option>
        <option value="america"> USE</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="checked" v-model="formValue.checked" true-value="yes" false-value="no">
    </div>
     <div>
    <label for="name">Skill List</label><br>
      <input type="checkbox" id="checked" v-model="formValue.skillList" value="CSS">
      <input type="checkbox" id="checked" v-model="formValue.skillList" value="HTML">

    </div>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // },
  data(){
    
    console.log("hello");
    let count=10;
    return {
      formValue:{
        name:'',
        selectedValue:'',
        multipleValue:[],
        checked:false,
        skillList:[]
      },
      count: count,
      name: 'Rajkumar',
      alertCheck: '<a href="/about">Hello </a>'
    }
  },
   methods:{
     testing(event){
       event.preventDefault();
       console.log(this.formValue)
     },
     add:(event)=>{
       console.log("i am here")
       console.log("here",event)
       return "10"
     }
  }
  }
 
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.Rajkumar{
  font-size: 100px;
  background-color: red;
}
</style>
