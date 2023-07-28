<template>

	<div class="tocadosRecentemente">

		<h2>Tocados Recentemente</h2>

		<div class="tocadosRecentementeGrid">
			<div class="tocadosRecentementeCard" v-for="item in content">
				<div class="tocadosRecentementeCardContent">
					<img class="cardCover" alt="cardCover" :src="item.imgSrc">
					<div class="cardText">
						<h3> {{ item.titulo }} </h3>
						<h4> {{ item.subTitulo }} </h4>
					</div>
				</div>
			</div>
		</div>

	</div>

</template>

<script>
import {defineComponent, ref} from "vue";

export default defineComponent({
	name: "TocadosRecentementeConteudo",

	setup() {

		const content = ref([]);

		content.value = [
			{
				imgSrc: 'https://www.covermesongs.com/wp-content/uploads/2020/02/billieeilish_whenweallfallasleepw_bs3v-500x500.jpg',
				titulo: 'When We All Fall Asleep, Where Do We Go?',
				subTitulo: 'Billie Eilish'
			},

			{
				imgSrc: 'https://upload.wikimedia.org/wikipedia/pt/4/4f/Evermore_-_Taylor_Swift.png',
				titulo: 'evermore (Deluxe)',
				subTitulo: 'Taylor Swift',
			},

			{
				imgSrc: 'https://cdns-images.dzcdn.net/images/cover/f571cb780b339ec087201b1cea53c3d9/500x500.jpg',
				titulo: 'Midnights',
				subTitulo: 'Taylor Swift',
			},

			{
				imgSrc: 'https://m.media-amazon.com/images/I/51cHJDF8uVL._UF1000,1000_QL80_.jpg',
				titulo: 'reputation',
				subTitulo: 'Taylor Swift',
			},
			
			{
				imgSrc: 'https://media.pitchfork.com/photos/5929b02b13d197565213a403/1:1/w_450%2Cc_limit/7bbf0819.jpg',
				titulo: 'BADLANDS(Deluxe)',
				subTitulo: 'Halsey'
			},

			{
				imgSrc: 'https://m.media-amazon.com/images/I/81fmr6cplSL._UF1000,1000_QL80_.jpg',
				titulo: 'Portals',
				subTitulo: 'Melanie Martinez'
			},

			{
				imgSrc: 'https://assets.vogue.com/photos/609bb445758287e5e091eeed/1:1/w_2000,h_2000,c_limit/Billie-Eilish-Happier-Than-Ever.jpeg',
				titulo: 'Happier Than Ever',
				subTitulo: 'Billie Eilish'
			},

			{
				imgSrc: 'https://m.media-amazon.com/images/I/41WzSwC+t8L._UF1000,1000_QL80_.jpg',
				titulo: 'Lover',
				subTitulo: 'Taylor Swift'
			},
		]

		return {
			content,
		}
	}
})
</script>

<style scoped>

.tocadosRecentemente {
	padding: 40px;
}

.tocadosRecentementeGrid {
	margin-top: 20px;
	display: grid;
	grid-template-rows: 1fr;
	grid-template-columns: repeat(8, 1fr);
	gap: 20px;
}

.tocadosRecentementeCard {
	background: var(--buttonBackground);
	display: flex;
	flex-direction: column;
	align-items: center;
	padding: 15px;
	border-radius: 7px;
}

.tocadosRecentementeCard:hover {
	background: var(--scrollBarBackground);
	transition: 200ms;
	cursor: pointer;
}

.cardCover {
	width: 140px;
	border-radius: 7px;
}

.cardText {
	display: flex;
	flex-direction: column;
	gap: 10px;
	white-space: nowrap;
	
}

.tocadosRecentementeCardContent {
	display: flex;
	flex-direction: column;
	gap: 25px;
	width: 140px;
	overflow: hidden;
}

h3 {
	font-size: 16px;
}

h4 {
	font-size: 14px;
	color: var(--textSecondary);
	font-weight: 500;
}

</style>