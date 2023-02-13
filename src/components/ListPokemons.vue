<script setup>
  const pokemon = defineProps(["name", "urlBaseSvg"]);

</script>

<template>
  <div class="col-4">
    <div class="card p-2 mb-3 cardListPokemon">
      <p class="text-center">{{ pokemon.name }}</p>
      <img 
      :src="urlBaseSvg" 
      class="card-img-top" 
      alt="Imagem Pokemon"
      height="75"
      />
    </div>
  </div>
</template>

<style scoped>
.cardListPokemon{
  background: #FF512F;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #F09819, #FF512F);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #F09819, #FF512F); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  cursor: pointer;
}

.cardListPokemon:hover{
  background: #FF512F;  /* fallback for old browsers */
  background: -webkit-linear-gradient(to right, #F09819, #FF512F);  /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(to right, #ffffff, #fae613); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.cardListPokemon img:hover{
  padding: .2rem;
}

</style>

