<template>

  <v-toolbar class="cyan" dark fixed>
    <v-toolbar-title class="mr-4 mb-0 pb-0">
      <span
      @click="navigateTo({name:'root'})"
      class="home">TabTracker
      </span>
      </v-toolbar-title>
    <v-toolbar-items>
      <v-btn 
      flat
      dark
      >
      Browser
      </v-btn>      
    </v-toolbar-items>
    <v-spacer></v-spacer>

    <v-toolbar-items v-if="$store.state.isUserLoggedIn">              
         <v-btn flat dark
         @click="navigateTo({name:'logout'})"> Log Out </v-btn>           
    </v-toolbar-items>
   
    <v-toolbar-items v-if="!$store.state.isUserLoggedIn">              
         <v-btn flat dark
         @click="navigateTo({name:'login'})"> Log In </v-btn>           
    </v-toolbar-items>
    <v-toolbar-items v-if="!$store.state.isUserLoggedIn">              
         <v-btn flat dark
         @click="navigateTo({name:'register'})"> Sign Up</v-btn>           
    </v-toolbar-items>
   
  </v-toolbar>

</template>

<script>
export default {

  methods: {
    navigateTo (route) {
      this.$router.push(route)
    }
  }
}
</script>

<style scoped>
.home:hover {
  cursor:pointer;
  color:rgb(214, 171, 225);
}
</style>

 

