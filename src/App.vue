<template>
  <div class="app"> 
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'app',
  components: {
    Navbar,
    Footer
  }
}
</script>


<style>
@import url("https://fonts.googleapis.com/css?family=Kanit");

 body {
   margin: 0 0 0 0; 
   font-family: "Kanit", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
 }
</style>
