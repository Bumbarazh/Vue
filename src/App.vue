<template>
  <div id="app">
    <input 
    type="text" v-model="doThing">
    <button v-if="toDos.length < 10" @click="addToTodos(doThing)">Add</button>
    <ol>
      <li v-for="(todo, index) of toDos" :key="index">
      {{todo}}
      <button @click="removeTodo(index)">Remove</button>
      </li>
    </ol>
  </div>
</template>

<script>


export default {
  name: 'App',
 
 data() {
   return {
    toDos: [],
    doThing: ''
   }
 },

 computed: {
    
 }, 

 methods: {
    addToTodos: function(doThing) {
        this.toDos.push(doThing);
      },

    removeTodo: function(index) {
        this.toDos = this.toDos.filter((el, i)  => i !== index);
    }  
    }
 }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
button {
  margin-left: 15px;
}
</style>
