<script setup>
  import { ref } from "vue";

  let num = ref (0)

</script>
<template>
<!--NAVBAR-->
<nav class="navbar navbar-expand-md navbar-dark bg-warning">
  <div class="container-fluid">
    <router-link class="navbar-brand" to="/">
      <img src="./assets/icon.svg" alt="" height="40" class="d-inline-block align-text-center">
      PokeTech
    </router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      
      <div class="navbar-nav">
        <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
        <router-link class="nav-link" to="/about">About</router-link>
      </div>

      <router-link class="logoPokemon mx-auto navbar-brand" to="/">
      <img src="./assets/logo.png" alt="logo-Pokemon" height="50">
      </router-link>
      
    </div>
  </div>
</nav>

<!--CONTENT-->
<div class="main">
  <router-view></router-view>
</div>

</template>

