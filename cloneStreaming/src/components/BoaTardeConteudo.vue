<template>
	<div class="boaTarde">
		<h1>Boa Tarde</h1>
		<div class="boaTardeGrid">
			<div class="boaTardeContent" v-for="item in content">
				<img class="cover" alt="cover" :src="item.imgSrc">
				<h3>{{ item.titulo }}</h3>
			</div>
		</div>
	</div>
</template>

<script>
import {defineComponent, ref} from "vue";

export default defineComponent({
	name: "BoaTardeConteudo",

	setup() {
		const content = ref([]);

		content.value = [
			{
				imgSrc: 'https://media.pitchfork.com/photos/5929b02b13d197565213a403/1:1/w_450%2Cc_limit/7bbf0819.jpg',
				titulo: 'BADLANDS(Deluxe)'
			},

			{
				imgSrc: 'https://media.pitchfork.com/photos/5a95e01230a20e587b2d1128/1:1/w_450%2Cc_limit/intonguesjoji.jpg',
				titulo: 'In Tongues(Deluxe)',
			},

			{
				imgSrc: 'https://www.covermesongs.com/wp-content/uploads/2020/02/billieeilish_whenweallfallasleepw_bs3v-500x500.jpg',
				titulo: 'When We All Fall Asleep, Where Do We Go?',
			},

			{
				imgSrc: 'https://i.pinimg.com/originals/78/6e/a3/786ea3d49748ab17966e4301f0f73bb6.jpg',
				titulo: 'dont smile at me',
			},

			{
				imgSrc: 'https://cdns-images.dzcdn.net/images/talk/968739990bc72325cd2923a3c3fba3de/1000x1000.jpg',
				titulo: 'Bocadinhas',
			},

			{
				imgSrc: 'https://upload.wikimedia.org/wikipedia/pt/4/4f/Evermore_-_Taylor_Swift.png',
				titulo: 'evermore (Deluxe)',
			},
		]

		return {
			content,
		}
	}
})
</script>

<style scoped>

.boaTarde {
	padding: 30px;
}

.boaTardeGrid {
	margin-top: 15px;
	display: grid;
	grid-template-rows: repeat(2, 1fr);
	grid-template-columns: repeat(3, 1fr);
	gap: 20px;
}

.boaTardeContent {
	display: flex;
	align-items: center;
	border-radius: 7px;
	gap: 8px;
	background: var(--mainPageCardBackground);
}

.boaTardeContent:hover {
	background: var(--mainPageCardBackgroundHover);
	transition: 200ms;
	cursor: pointer;
}

.cover {
	width: 80px;
	border-radius: 7px 0 0 7px;
}

</style>