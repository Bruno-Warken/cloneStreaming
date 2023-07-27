<template>
	<div class="containerBottomListas">
		<div v-for="item in recentes" class="listaContent">
			<img class="albumCover" alt="albumCover" :src="item.imgScr">
			<div class="listaContentText">
				<h4>{{ item.titulo }}</h4>
				<h5>{{ item.subTitulo }}</h5>
			</div>
		</div>
	</div>
</template>

<script>
import {defineComponent, ref} from "vue";

export default defineComponent({
	name: "RecentesConteudo",
	
	setup(){
		const recentes = ref([]);
		
		recentes.value = [
			{
				imgScr: 'https://media.pitchfork.com/photos/5a95e01230a20e587b2d1128/1:1/w_450%2Cc_limit/intonguesjoji.jpg',
				titulo: 'In Tongues(Deluxe)',
				subTitulo: 'Álbum - Joji'
			},

			{
				imgScr: 'https://www.covermesongs.com/wp-content/uploads/2020/02/billieeilish_whenweallfallasleepw_bs3v-500x500.jpg',
				titulo: 'When We All Fall Asleep, Where Do We Go?',
				subTitulo: 'Álbum - Billie Eilish'
			},

			{
				imgScr: 'https://i.pinimg.com/originals/78/6e/a3/786ea3d49748ab17966e4301f0f73bb6.jpg',
				titulo: 'dont smile at me',
				subTitulo: 'Álbum - Billie Eilish'
			},

			{
				imgScr: 'https://assets.vogue.com/photos/609bb445758287e5e091eeed/1:1/w_2000,h_2000,c_limit/Billie-Eilish-Happier-Than-Ever.jpeg',
				titulo: 'Happier Than Ever',
				subTitulo: 'Álbum - Billie Eilish'
			},

			{
				imgScr: 'https://cdns-images.dzcdn.net/images/talk/968739990bc72325cd2923a3c3fba3de/1000x1000.jpg',
				titulo: 'Bocadinhas',
				subTitulo: 'Podcast - Lucas Inutilismo'
			},

			{
				imgScr: 'https://m.media-amazon.com/images/I/81fmr6cplSL._UF1000,1000_QL80_.jpg',
				titulo: 'Portals',
				subTitulo: 'Álbum - Melanie Martinez'
			},
			
			{
				imgScr: 'https://upload.wikimedia.org/wikipedia/pt/4/4f/Evermore_-_Taylor_Swift.png',
				titulo: 'evermore',
				subTitulo: 'Álbum - Taylor Swift'
			},
			
			{
				imgScr: 'https://m.media-amazon.com/images/I/41WzSwC+t8L._UF1000,1000_QL80_.jpg',
				titulo: 'Lover',
				subTitulo: 'Álbum - Taylor Swift'
			},
			
			{
				imgScr: 'https://upload.wikimedia.org/wikipedia/pt/f/f8/Taylor_Swift_-_Folklore.png',
				titulo: 'folklore',
				subTitulo: 'Álbum - Taylor Swift'
			},
			
			{
				imgScr: 'https://upload.wikimedia.org/wikipedia/pt/c/c8/SZA_-_SOS.png',
				titulo: 'SOS',
				subTitulo: 'Álbum - SZA'
			},
		]
		
		return{
			recentes,
		}
		
	}
})
</script>

<style scoped>

.containerBottomListas {
	height: 560px;
	overflow-y: auto;
	overflow-x: hidden;
}

.containerBottomListas::-webkit-scrollbar {
	width: 10px;
}

.containerBottomListas::-webkit-scrollbar-thumb {
	background: var(--scrollBarBackground);
}

.listaContent {
	display: flex;
	margin: 10px 10px 15px;
	white-space: nowrap;
	width: 100%;
}

.listaContent:hover {
	background: var(--listaContentHover);
	transition: 200ms;
	cursor: pointer;
}

.listaContentText {
	display: flex;
	flex-direction: column;
	justify-content: center;
	gap: 5px;
	margin-left: 5px;
}

.listaContentText > h4 {
	font-weight: 500;
	color: var(--textPrimary);
}

.listaContentText > h5 {
	font-weight: 500;
	color: var(--textSecondary);
}

.albumCover {
	width: 50px;
	height: 50px;
}

</style>