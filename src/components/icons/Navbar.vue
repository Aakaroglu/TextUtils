

<script setup>
import { inject } from "vue";

        const darkMode = inject("darkMode");
</script>

<template>
<nav class="navbar navbar-expand-lg" :class="darkMode?'navbar-dark bg-dark text-white':'navbar-white bg-white text-dark'">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">TextUtils</a>
    <!-- <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button> -->
    <!-- <div class="collapse navbar-collapse" id="navbarSupportedContent"> -->
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#" style="margin-top: 10px;  ">Home</a>
        </li>
      </ul>
      <div class="d-flex" >
        <div class="form-check form-switch">
  <input class="form-check-input" v-model="darkMode" type="checkbox" role="switch"
   id="flexSwitchCheckDefault">
  <label class="form-check-label" 
  for="flexSwitchCheckDefault">Enable {{darkMode?'LightMode':'DarkMode'}}</label>
        </div>
    </div>
    <!-- </div> -->
  </div>
</nav>
</template>
<style lang="scss" scoped>

</style>