<script setup>
import { onMounted, ref, reactive, computed } from "vue";
import ListPokemon from "../components/ListPokemon.vue";
import CardPokemonSelected from "../components/CardPokemonSelected.vue";

const pokemons = ref([]);
const urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/");
const searchPokemonField = ref("");
const pokemonSelected = ref(null);
const loading = ref(false);
const offset = ref(0);

onMounted(() => {
  loadPokemonList();
});

const loadPokemonList = async () => {
  loading.value = true;
  try {
    const response = await fetch(`https://pokeapi.co/api/v2/pokemon?limit=20&offset=${offset.value}`);
    const data = await response.json();
    pokemons.value = [...pokemons.value, ...data.results];
    offset.value += 20;
  } catch (error) {
    console.error("Error loading Pokémon list:", error);
  } finally {
    loading.value = false;
  }
};

const pokemonsFilter = computed(() => {
  if (pokemons.value && searchPokemonField.value) {
    return pokemons.value.filter(pokemon =>
      pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
    );
  }
  return pokemons.value;
});

const selectPokemon = async (pokemon) => {
  loading.value = true;
  try {
    const response = await fetch(pokemon.url);
    const data = await response.json();
    pokemonSelected.value = data;
  } catch (error) {
    console.error("Error selecting Pokémon:", error);
  } finally {
    loading.value = false;
  }
};

const handleCardScroll = () => {
  const cardContainer = document.querySelector('.card-list');
  const { scrollTop, clientHeight, scrollHeight } = cardContainer;

  if (scrollTop + clientHeight >= scrollHeight - 10 && !loading.value) {
    loadPokemonList();
  }
};
</script>
<template>
  <main>
   <div class="container">
    <div class="row mt-4">
    <div class="col-sm-12 col-md-6">
  <CardPokemonSelected
  :name="pokemonSelected?.name"
  :xp="pokemonSelected?.base_experience"
  :height="pokemonSelected?.height"
  :img ="pokemonSelected?.sprites.other.dream_world.front_default"
  :loading="loading"
  />
  <br/>
  <!--observar essa linha-->
    </div>
    <div class="col-sm-12 col-md-6" >
      <div class="mb-3">
  <label hidden for="SerchPokemonField" class="form-label">Pesquisar</label>
  <input v-model="searchPokemonField" type="text" class="form-control" id="seachPokemonField" placeholder="Pesquisar...">
</div>
    <div class="card card-list  "ref="cardContainer" @scroll="handleCardScroll">
      <div class="card-body row">
     <ListPokemon
     v-for="pokemon in pokemonsFilter"
     :key ="pokemon.name"
     :name="pokemon.name"
     :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] +'.svg'"
     @click ="selectPokemon(pokemon)"
     />
    </div>
    <!-- <ul>
        <li v-for="pokemon in pokemons"
        :key="pokemon.name"
        >
        {{ pokemon.name }}
        </li>*/
      </ul>-->
          </div>
        </div>
      </div>
    </div>
  
  <div id="loadMoreTrigger"></div>
  </main>
</template>
<style scoped>

.card-list
{
  max-height: 500px;
  overflow-y: scroll;
  overflow-x:hidden ;
}
</style>