<template>

  <div>Hello {{name}}</div>
  <div v-html="name"></div> 
  <div v-html="alertCheck"></div>
  <div :id="name">{{name}}</div>
  <div class="Rajkumar">{{name}}</div>
  <h1>{{count}}</h1>
  <button @mouseover="count+=1">increase</button>
    <button @click="count-=1">decrease</button>
    <div>
      {{formValue}}
    </div>
  <form @submit="testing">
    <div v-bind:style="{backgroundColor:'red'}"> 
      <label for="name">Name</label><br>
      <input type="text" id="name" placeholder="Enter the name" v-model.trim="formValue.name">
    </div>
    <div> 
      <label for="name">Enter Number</label><br>
      <input type="text" id="name" placeholder="Enter the number" v-model.number="formValue.age">
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

  <!-- other diretives
  v-once load the page only once.
  v-pre  
   -->

   <!-- Computed Properties -->

   <h1>{{firstName}} {{lastName}}</h1>
   <h1>{{fullName}}</h1>

   <!-- components -->
   <div v-bind:style='{display:"flex"}'>
    <helloWorld msg="hello"/>
   <helloWorld/>
   <helloWorld/>
   <helloWorld/>
   </div>
    <!-- <template> -->
    <posts :msg="data"/>
    <!-- </template> -->
    <button @click="getPosts">Get all Posts</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Posts from './components/Posts.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Posts
  },
  data(){
    console.log("hello");
    let count=10;
    return {
      data:null,
      firstName:'rajkumar',
      lastName: 'Jakkula',
      formValue:{
        name:'',
        selectedValue:'',
        multipleValue:[],
        checked:false,
        skillList:[],
        age:null
      },
      count: count,
      name: 'Rajkumar',
      alertCheck: '<a href="/about">Hello </a>'
    }
  },
   computed:{
       fullName(){
         return `${this.firstName} ${this.lastName}`
       }
     },
   methods:{
     getPosts(){
       axios.get('https://jsonplaceholder.typicode.com/posts')
       .then(data=>
       this.data=data
       )
       .catch(err=>
       console.log(err)
       )
     },
     testing(event){
       console.log("Hello fron testing")
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
