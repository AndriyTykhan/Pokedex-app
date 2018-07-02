<template>
  		<div class="card-block" v-if="pokemon">
  				<img  :src=" 'https://img.pokemondb.net/sprites/omega-ruby-alpha-sapphire/dex/normal/' + pokemon.name  + '.png' ">
  					<h4 class="cart-title">{{pokemon.name}}</h4>
  					<table class="table-bordered">
  						<tr>
  							<td>Type</td>
  							<td>{{pokemon.types[0].type.name}}</td>
  						</tr>
  						<tr>
  							<td>Attack</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>Defence</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>HP</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>SP Attack</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>SP Defence</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>Speed</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>Weight</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  						<tr>
  							<td>Total Moves</td>
  							<td>{{pokemon.height}}</td>
  						</tr>
  					</table>


  			<!--
					<p class="">Type: {{pokemon.stats[0].base_stat}}</p>
					<p class="">Attack: {{pokemon.height}}</p>
					<p class="">Defence: {{pokemon.stats[0].base_stat}}</p>
					<p class="">HP: {{pokemon.base_experience}}</p>
					<p class="">SP Attack: {{pokemon.base_experience}}</p>
					<p class="">SP Defence: {{pokemon.stats[0].base_stat}}</p>
					<p class="">Speed: {{pokemon.stats[0].base_stat}}</p>
					<p class="">Weight: {{pokemon.weight}}</p>
					<p class="">Total moves: {{pokemon.stats[0].base_stat}}</p>


				-->
			</div>
</template>

<script>
	export default {
		name: 'PokemonCard',
		props: ['id'],
		data() {
			return {
				pokemon: ''	
			}
		},
		methods: {
			fetchCharacter(id) {
				fetch(`https://pokeapi.co/api/v2/pokemon/${id}/`)
					.then(response => response.json())
					.then(json => this.pokemon = json)
			}
		},
		created() {
			this.fetchCharacter(this.id)
		},
		updated() {
			this.fetchCharacter(this.id)
		}
	}


</script>

<style>
	table {
		width: 100%;

	}
	td {
		text-align: center !important;
		padding: 10px !important;
	}
	.card-block {
		border: 2px solid #4FC08D;
		border-radius: 4px;
		cursor: pointer;
		
	}
	.card-text {
		border: 1px solid green;
		background: rgb(20,150,20);
	}
</style>