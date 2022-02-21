<template>
  <v-app>
    <Login/>
  </v-app>
</template>

<script>
 //import Login from './components/Auth/Login'
import Login from './components/Auth/Login.vue'; 

// import Signup from './components/Auth/Signup'
//import Todo from './components/Todo'
export default {
  created () {
  },
  name: 'App',
  components: {
    Login
    //Todo
},

};
</script>
