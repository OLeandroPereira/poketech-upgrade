<script setup>
  const pokemon = defineProps(["img", "name", "hp", "loading"])

</script>

<template>
  <div class="CardPokemonSelected"
  :class="loading ? '' : 'animate__animated animate__bounceInRight'"
  >
    <img 
    v-if="pokemon.name"
    :src="pokemon.img"
    height="300" 
    class="card-img-top pt-2" 
    :alt="pokemon.name"
    >

    <img 
    v-else
    src="../assets/egg_pokemon.svg"
    class="card-img-top pt-2 first-initial" 
    :alt="pokemon.name"
    >

    <div class="card-body text-center">
      <h5 class="card-title text-center">{{ pokemon.name || '???'}}</h5>
      <hr>
      
      <div class="row p-3">
        <div class="col" style='text-align:left'>
          <ul class="stats">
            <h4>Base de stats:</h4>
            <li><strong>HP:</strong>{{ pokemon.hp }}</li>
            <li><strong>ATTACK:</strong>{{ pokemon.attack }}</li>
            <li><strong>DEFENSE:</strong>{{ pokemon.defense }}</li>
            <li><strong>SPECIAL ATTACK:</strong>{{ pokemon.specialAttack }}</li>
            <li><strong>SPECIAL DEFENSE:</strong>{{ pokemon.specialDefense }}</li>
            <li><strong>SPEED:</strong>{{ pokemon.speed }}</li>
          </ul>
        </div>
        
        <div class="developer col">
          <img src="../assets/Foto.png" class="card-img-top" alt="Desenvolvedor do App">
          <p class="mt-2">Leandro Pereira</p>
          <strong>Desenvolvedor<br>Front-end</strong>
        </div> 
      </div>
    </div>
  </div>
</template>

<style scoped>
  .card-body {
    padding: 0;
  }

  .developer {
    line-height: 15px;

  }
  .developer img {
    max-width: 40%;
    border-radius: 50%;
    border: 9px solid #eebe65;
  }

  .CardPokemonSelected {
    max-height: 100vh;
    color: #fff;
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,96,121,1) 35%, rgba(0,212,255,1) 100%);
  }
  
  .stats {
      list-style: none;
  }

  .first-initial {
    height: 250px;
  }

  @media (max-width: 600px) {
   
    .descricao {
      height: 50px;
    }
    
    .developer img {
      max-width: 60%;

      border: 3px solid #eebe65;
    }

    .first-initial {
      height: 150px;
  }
    

  }

</style>