<script setup>
const pokemon = defineProps(["name","type","xp","height","img","loading"])
</script>

<template>
    <div class="card CardSelected"  style="width: 28rem;">
  <img 
  v-if ="pokemon.name"
  :src="pokemon.img" height="200" class="card-img-top" alt="pokemon.name">
  <img
  v-else 
  src="/src/assets/pokebolaoficial.png" height="200" class="card-img-top" alt="????">
  <div class="card-body row">
    <h5 class="card-title text-center">{{pokemon.name}}</h5>
    <hr>
    <div class="row">
        <section class="col">
            <strong>XP:</strong>
            <span>{{pokemon.xp}}</span>
        </section>
        <section class="col">
            <strong>Altura:</strong>
            <span>{{pokemon.height}}</span>
        </section>
    </div>
  </div>
</div>
</template>
<style scoped>

.CardSelected:hover
{
    background: rgb(20, 102, 130);
    background: radial-gradient(circle rgba(20, 17, 11, 0.866)0% rgba(16, 26, 25, 0.981)100%);
    padding: .9rem;
}

.CardSelected img:hover
{
    padding: .1rem;
}

</style>