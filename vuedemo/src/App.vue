<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome!! this is my first vue.app"/> -->
  <div id="app">
    <h1>{{getTitle}}</h1>
    <li @repeat='todos'
        @click="done = !done"
        class="{{done ? 'done' : ''}}"
    >{{todos.content}}</li>
      <!-- <UserProfile/> -->
  </div>
</template>

<script>
//import { computed } from '@vue/runtime-core'
//import UserProfile from './components/UserProfile'

export default {
  name: 'App',
  data() {
    return{
      title: 'todos',
      todos: [
        {
          done:true,
          content:'Learn Javascript'
        },{
          done:false,
          content:'Learn Vue.js'
        }
      ]
    }
  },
  computed: {
      getTitle() {
        return  this.capitalize(this.title);
      }
    },
  methods:{
     capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.toUpperCase()
    }
  }
  //  components: {
  //    UserProfile
  //  }
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
</style>
