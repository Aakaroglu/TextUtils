<script setup>
import { provide, ref, watchEffect } from 'vue';
import Navbar from './components/icons/Navbar.vue';
import Home from './pages/Home.vue';


const darkMode = ref(false);

provide("darkMode",darkMode);

watchEffect("darkMode",darkMode);

watchEffect(()=> {
  if(darkMode.value) {
    document.body.style.backgroundColor='#2b2f32';
  }
  else{
    document.body.style.backgroundColor="white";
    

  }
})

</script>
<template>

  <Navbar/>
  <Home/>

</template>



<style lang="scss" scoped></style>