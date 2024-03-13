<script setup>
import { ref } from 'vue';
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img src="./assets/icon.png" alt="" height="40" class="d-inline-block align-text-center">
        Poketest
      </router-link>
      
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
            </button>
             <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <router-link class="nav-link" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/about">Sobre</router-link>
        </li>
        
      </ul>
    </div>
  </div>
</nav>
<div class="main">
  <router-view></router-view>
</div>



<footer class="bg-primary text-light">
  <div> Criado por Gabriel Barros em {{ new Date().getFullYear()}}</div>
</footer>

</template>


<style>
footer
{
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  align-items:center;
  justify-content: center;
  height: 56px;
}
</style>

