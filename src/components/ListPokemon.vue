<script setup>
const pokemon = defineProps(["name","urlBaseSvg"])
</script>

<template>

    <div class="col-4">
        <div class="card p-2 mb-3 cardListPokemon">
            <p class="text-center">{{pokemon.name}}</p>
            <img :src="urlBaseSvg" class="card-img-top" alt="..."
            height="120"
            />
        </div>
    </div>

</template>

<style scoped>
.cardListPokemon:hover
{
    background: rgb(127, 210, 236);
    background: radial-gradient(circle rgba(243 60% 12% / 0.5)0% rgba(9, 239, 227, 0.8)100%);
    padding: .9rem;
}



.cardListPokemon img:hover
{
    padding: .1rem;
}

</style>