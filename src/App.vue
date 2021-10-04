<template>
  <div id="app">
     <Users/>
  </div>
</template>

<script>
import Users from './components/Users.vue'

export default {
  name: 'App',
  components: {
    Users
  }
}
</script>


<style>
  *{
    margin:0px;
    padding:0px;
    
  }
#app {
  width:100%;
  height: 100vh;
 
background-color: #00DBDE;
background-image: linear-gradient(100deg, #00DBDE 0%, #FC00FF 100%);
 }

</style>

