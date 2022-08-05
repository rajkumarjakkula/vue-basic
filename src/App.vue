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
      {{formValues}}
    </div>
  <form>
    <div v-bind:style="{backgroundColor:'red'}"> 
      <label for="name">Name</label><br>
      <input type="text" id="name" placeholder="Enter the name" v-model="formValues.name">
    </div>
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
      formValues:{
        name:''
      },
      count: count,
      name: 'Rajkumar',
      alertCheck: '<a href="/about">Hello </a>'
    }
  },
   methods:{
     
     add:(event)=>{
       console.log("i am here")
       console.log("here",event)
       return {Hell:"10"}
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
