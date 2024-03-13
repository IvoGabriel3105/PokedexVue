<script setup>
</script>
<template>
  <div class="about">
    <h1>Referencias</h1>
  </div>
  <div class="row" id="referencia">
  <div class="col-sm-6 mb-2 mb-sm-2">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Vue js</h5>
        <p class="card-text">Aplicação desenvolvida com Vue.js, HTML, CSS, e Node.js, composition API.</p>
        <a href="https://vuejs.org/" class="btn btn-primary" target=”_blank”>Site Oficial</a>
      </div>
    </div>
  </div>
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">API</h5>
        <p class="card-text">API utilizada no projeto pokeApi</p>
        <a href="https://pokeapi.co/" class="btn btn-primary" target=”_blank”>Site Oficial</a>
      </div>
    </div> 
    <br/>
  </div>
 
  <div class="col-sm-6 mb-2 mb-sm-0">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">infinity Scroll</h5>
        <p class="card-text">Principal referencia para infinity scroll</p>
        <a href="https://www.npmjs.com/package/vue-infinite-scroll" class="btn btn-primary" target=”_blank”>Site Oficial</a>
      </div>
    </div>
  </div>
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Bootstrap</h5>
        <p class="card-text">Responsavel por estilização das paginas e responsividade </p>
        <a href="https://getbootstrap.com/docs/5.3/getting-started/introduction/" class="btn btn-primary" target=”_blank”>Site Oficial</a>
      </div>
    </div>
  </div>
</div>
</template>

<style>
/*@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }*/
  h1
  {
    text-align: center;
    width: 100%;
  }
  #referencia{
  padding: .9rem;
  
  }
  #referencia:hover{
  padding: .10rem;
  
  }
</style>
