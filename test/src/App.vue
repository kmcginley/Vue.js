// this is your output
<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
   <export1 v-bind:todos3="todos2" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>

import export1 from './components/Todos'
export default {
  name: 'App',
  components: {
    // name from export default
    export1
  },
  data() {
    return {
      todos2: [
        {
          id: 1,
          title: "Todo One",
          completed: false
        },        
        {
          id: 2,
          title: "Todo Two",
          completed: true
        },        
        {
          id: 3,
          title: "Todo Three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos2 = this.todos2.filter(todo => todo.id !== id)
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

</style>
