<template>
  <div class="container mt-4">
    <div class="card">
      <h1 class="text-center m-5">Teste da CopyBase</h1>
      <div class="card-body p-3">
        <p>Você irá construir uma aplicação para listagem e busca de pokemons. É uma aplicação simples, onde iremos buscar por um determinado pokémon, pelo seu nome, para termos acesso às suas propriedades requisitadas através da PokeAPI v2. </p>


        <p>Nossa ideia de interface é uma tela com apenas um campo de busca no centro da tela, que ao ser acionado com o nome do pokémon, irá submeter esta pesquisa para a PokeAPI, retornando as informações do pokémon buscado e de suas evoluções (Evolution Chains).</p> 

        <p>Para cada um dos pokémons listados (o pesquisado e suas evoluções), gostaríamos de ver seu nome e sua imagem.</p>


        <p>Quando clicarmos em um pokémon listado, queremos listar suas principais características (hp, attack, defense, special attack, special defense e speed). Obviamente quanto mais informações você mostrar melhor (organizadas, usando princípios básicos de UI/UX), então fique a vontade para exibir o que mais achar interessante.</p>

      </div>
      <hr>
      <div class="p-3">
        <h1 class="text-center mb-5">Agradecimento</h1>
        <p>Gostaria de aproveitar e agradecer a oportunidade de participar desse processo tecnico. Será uma enorme alegria, se eu for um dos selecionados para a próxima etapa, darei o meu máximo, para responder a espectativa da empresa.</p>
      </div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
