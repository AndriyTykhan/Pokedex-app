<template>
	<div>
		<div class="row">
			<div class="col">
				<div class="row cards">
						<PokemonCard 
							v-for="id in idList"
							:key="id.id"
							:id="id"
							@logId='log'
							class="col-4"
						/>
						<button class="btn btn-primary load" @click="load">Load More</button>
				</div>
			</div>

			<div class="col" v-if="selectedId">
				<PokemonChoosen	
					:id="selectedId"
					class="choosen"
				/>
			</div>
		</div>

	</div>
</template>

<script>
	import PokemonCard from './PokemonCard.vue'
	import PokemonChoosen from './PokemonChoosen.vue'

	export default {
		name: 'PokemonPage',
		data() {
			return {
				idList: [1,2,3,4,5,6,7,8,9],
				selectedId: ''
			}
		},
		methods: {
			load() {
					this.idList = this.idList.map(el => el + 9);
					console.log(this.idList)
			},
			log(id) {
				this.selectedId = id;
				//console.log(id)
			},
			filter() {
				console.log(this.id);
			},
			
		},
		
		components: {
			PokemonCard,
			PokemonChoosen

		}
	}
</script>

<style>

	.choosen {
		margin: 0 auto;
		width: 60%;
	}
	.load {
		margin-top: 10px;
		width: 100%;
	}
</style>