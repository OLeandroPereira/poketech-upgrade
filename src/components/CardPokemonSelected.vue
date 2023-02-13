<script setup>
  const pokemon = defineProps(["img", "name", "hp", "loading"])

</script>

<template>
  <div class="CardPokemonSelected mt-5"
  :class="loading ? '' : 'animate__animated animate__flipInX'"
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
      
        <div class="row">
          <div class="col" style='text-align:left'>
            <h5>Base de stats:</h5>
            <ul class="stats">
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
            <p>Desenvolvedor<br>Front-end</p>
            
            <p>Leandro Pereira</p>
          </div> 
      </div>
    </div>
  </div>
</template>

<style scoped>
  .developer {
    line-height: 15px;

  }
  .developer img {
    max-width: 40%;
    border-radius: 50%;
    border: 9px solid #eebe65;
  }

  .CardPokemonSelected {
    max-height: 70vh;
    color: #fff;
    background: rgb(2,0,36);
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,96,121,1) 35%, rgba(0,212,255,1) 100%);
  }

  .first-initial {
    height: 250px;
  }

  @media (max-width: 600px) {
   
   

    .descricao {
      height: 50px;
    }
    
    .developer img {
      height: 50px;
    }

    .stats {
      list-style: none;
    }

  }

</style>