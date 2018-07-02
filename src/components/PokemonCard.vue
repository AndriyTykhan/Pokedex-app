<template>
  		<div class="card-block"  v-if="pokemon" @click="logId">
  				<img   :src=" 'https://img.pokemondb.net/sprites/omega-ruby-alpha-sapphire/dex/normal/' + pokemon.name  + '.png' ">
				<h4 class="cart-title">{{pokemon.name}}</h4>
				<p class="card-text" :style="{backgroundColor: TYPE_COLOR[pokemon.types[0].type.name]}">{{pokemon.types[0].type.name}}</p>
			</div>
</template>

<script>
	export default {
		name: 'PokemonCard',
		props: ['id'],
		data() {
			return {
				pokemon: '',
				fisd: 0,
				TYPE_COLOR: {
		            "grass": "#78C850",
		            "poison": "#A040A0",
		            "fire": "#F08030",
		            "flying": "#A890F0",
		            "water": "#6890F0",
		            "bug": "#A8B820",
		            "normal": "#A8A878",
		            "electric": "#F8D030",
		        },
			}
		},
		methods: {
			fetchCharacter(id) {
				fetch(`https://pokeapi.co/api/v2/pokemon/${id}/`)
					.then(response => response.json())
					.then(json => this.pokemon = json)
			},
			logId() {
				//console.log(this.id)
				this.$emit('logId', this.id)
			}
		},
		mounted() {
			
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
	.card-block {
		border: 2px solid #4FC08D;
		border-radius: 4px;
		cursor: pointer;
		
	}
	.card-text {
		border-radius: 5px;
		width: 50%;
		margin-bottom: 5px;
	}
</style>