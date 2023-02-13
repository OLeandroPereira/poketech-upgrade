<script setup>
  import { ref } from "vue";

  let num = ref (0)

</script>
<template>
<!--NAVBAR-->
<nav class="navbar navbar-expand-lg navbar-primary bg-warning">
  <div class="container-fluid">
    <router-link class="navbar-brand" to="/">
      <img src="./assets/icon.svg" alt="" width="30" height="24" class="d-inline-block align-text-top">
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
      <router-link class="mx-auto navbar-brand" to="/">
      <img src="./assets/logo.png" alt="" width="100" height="50" class="d-inline-block">
      </router-link>
    </div>
  </div>
</nav>

<!--CONTENT-->
<div class="main">
  <router-view></router-view>
</div>

</template>

<style>
 
 </style>
