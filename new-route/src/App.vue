<template>
  <v-app>
  <router-view></router-view>
  <v-bottom-navigation fixed
    color="primary"
  >
    <v-btn to="/login">
      Login
    </v-btn>
    <v-btn to="/signup">
      Signup
    </v-btn>
  </v-bottom-navigation>
  </v-app>
</template>

<script>

//import Login from './components/Auth/Login'
//import Login from './components/Auth/Login-n.vue'; 

// import Signup from './components/Auth/Signup'
export default {
  created () {
  },
  name: 'App',
  components: {
    
},

};
</script>


