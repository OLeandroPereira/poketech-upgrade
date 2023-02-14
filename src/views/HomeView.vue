
<script setup>
import { onMounted, reactive, ref, computed, watch } from "vue";
import ListPokemons from "../components/ListPokemons.vue";
import CardPokemonSelected from "../components/CardPokemonSelected.vue";


let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")
let pokemons = reactive(ref());
let searchPokemonField = ref("")
let pokemonSelected = reactive(ref());
let loading = ref(false)



onMounted(()=>{
  fetch("https://pokeapi.co/api/v2/pokemon?limit=200&offset=0")
  .then(res => res.json())
  .then(res => pokemons.value = res.results);
})

const pokemonsFiltered = computed(()=>{
  if(pokemons.value && searchPokemonField.value){
    return pokemons.value.filter(pokemon=>
      pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
    )
  }
})

const selectPokemon = async (pokemon) => {
  loading.value = true;
   await fetch(pokemon.url)
  .then(res => res.json())
  .then(res => pokemonSelected.value = res)
  .catch(err => alert(err))
  .finally(()=> loading.value = false)

console.log(pokemonSelected)

}

</script>

<template>
  <main class="body">
      <div class="container">
        <div class="row mt-4">
          <div class="col-sm-12 col-md-6">
            
            <CardPokemonSelected 
            :name="pokemonSelected?.name"  
            :img="pokemonSelected?.sprites.other.dream_world.front_default"
            :hd="pokemonSelected?.stats[0].base_stat"
            :attack="pokemonSelected?.stats[1].base_stat"
            :defense="pokemonSelected?.stats[2].base_stat"
            :special_attack="pokemonSelected?.stats[3].base_stat"
            :special_defense="pokemonSelected?.stats[4].base_stat"
            :speed="pokemonSelected?.stats[5].base_stat"
            :loading="loading"
            />             
             

          </div>
          
          <div class="col-sm-12 col-md-6 m-auto">
            <div class="card card-list">
              <div>

                <div>
                  <label 
                  hidden 
                  for="searchPokemonField" 
                  class="form-label">
                  Pesquisar Pokemon...
                  </label>

                  <input 
                  v-model="searchPokemonField"
                  type="text" 
                  class="form-control" 
                  id="searchPokemonField" 
                  placeholder="Pesquisar Pokemon...">
                </div>

              </div>
            </div>

            <div class="card-list">
              <div class="card-body row">
                <ListPokemons 
                v-for="pokemon in pokemonsFiltered"
                :key="pokemon.name"
                :name="pokemon.name"
                :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] + '.svg'"
                @click="selectPokemon(pokemon)" 
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    
  </main>
</template>

<style scoped>
   .card-list {
    max-height: 70vh;
    max-height: 545px;
    overflow-y: scrool;
    overflow-x: hidden;
    margin: 0;
  }

  @media (max-width: 600px) {
   .card-body {
    max-height: 160px;
   }
    
  }  

</style>

