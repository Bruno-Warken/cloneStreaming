<template>

	<div class="tocadosRecentemente">

		<h2>{{titulo}}</h2>

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
import {Types} from "@/assets/Utils";

export default defineComponent({
	name: "Sugestoes",
	props: {
		type: Number,
	},
	
	setup(props) {

		const content = ref([]);
		const titulo = ref('');

		const recents = [
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

		const podcasts = [
			{
				imgSrc: 'https://cdns-images.dzcdn.net/images/talk/968739990bc72325cd2923a3c3fba3de/264x264.jpg',
				titulo: 'Bocadinhas',
				subTitulo: 'Lucas Inutilismo'
			},

			{
				imgSrc: 'https://i.scdn.co/image/ab6765630000ba8a0d11957abedeab4e177cd064',
				titulo: 'Dead Meat',
				subTitulo: 'Chelsea Rebecca, James A Janisse',
			},

			{
				imgSrc: 'https://i.scdn.co/image/ab6765630000ba8a113ad7d3cacdd22555802f23',
				titulo: 'The Basemant Yard',
				subTitulo: 'Santagato Studios',
			},

			{
				imgSrc: 'https://yt3.googleusercontent.com/1AjgyxU-4_gxjMSS_-kuNwNryVsc0fzrDfTImX1Urh8hu6AMoNDcj-TGNug2v6qSvP3aXhodsw=s900-c-k-c0x00ffffff-no-rj',
				titulo: 'Goons',
				subTitulo: 'The Goons Podcast',
			},

			{
				imgSrc: 'https://cdns-images.dzcdn.net/images/talk/fed12b3b21729cd25242ca241079820e/1000x1000.jpg',
				titulo: 'League of Loreheads',
				subTitulo: 'Rebecca, Mark, John'
			},

			{
				imgSrc: 'https://i.scdn.co/image/ab6765630000ba8aacfd8efb264a9f264973b1ee',
				titulo: 'The Boulet Brothers',
				subTitulo: 'Boulet Brothers & Studio71'
			},
		]

		const mixes = [
			{
				imgSrc: 'src/assets/imagens/mixBrockhampton.jpg',
				titulo: 'Mix de BROCKHAMPTON',
				subTitulo: 'Kevin Abstract, KIDS, SEE GHOSTS e mais'
			},

			{
				imgSrc: 'src/assets/imagens/mixBillieEilish.jpg',
				titulo: 'Mix de Billie Eilish',
				subTitulo: 'Joji, Taylor Swift e Alec Benjamin',
			},

			{
				imgSrc: 'src/assets/imagens/mixRelax.jpg',
				titulo: 'Mix relax',
				subTitulo: 'SZA, Taylor Swift, Halsey e mais',
			},

			{
				imgSrc: 'src/assets/imagens/mixMelancolico.jpg',
				titulo: 'Mix melancólico',
				subTitulo: 'Joji, MISSIO, Jaymes Young e mais',
			},

			{
				imgSrc: 'src/assets/imagens/mixAnos2010.jpg',
				titulo: 'Mix anos 2010',
				subTitulo: 'Glass Animals, Panic!At The Disco e mais'
			},

			{
				imgSrc: 'src/assets/imagens/mixAnos2000.jpg',
				titulo: 'Mix anos 2000',
				subTitulo: 'Ikimonogakari, YUI, Taylor Swift e mais'
			},

			{
				imgSrc: 'src/assets/imagens/mixPop.jpg',
				titulo: 'Mix pop',
				subTitulo: 'Doja Cat, Alec Benjamin, Halsey e mais'
			},

			{
				imgSrc: 'src/assets/imagens/mixHipHop.jpg',
				titulo: 'Mix hip hop',
				subTitulo: 'Connor Price, Post Malone e mais'
			},
		]
		
		if(props.type === Types.Recents){
			content.value = recents;
			titulo.value = 'Tocados recentemente';
		} else if(props.type === Types.Podcast){
			content.value = podcasts;
			titulo.value = 'Seus episódios';
		}else {
			content.value = mixes;
			titulo.value = 'Seus mixes mais ouvidos';
		}

		return {
			content,
			titulo,
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
}

.tocadosRecentementeCardContent {
	display: flex;
	flex-direction: column;
	gap: 25px;
	width: 140px;
	overflow: hidden;
}

h3 {
	white-space: nowrap;
	font-size: 16px;
}

h4 {
	font-size: 14px;
	color: var(--textSecondary);
	font-weight: 500;
}

</style>