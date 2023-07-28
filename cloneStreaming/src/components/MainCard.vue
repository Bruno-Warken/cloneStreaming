<template>

	<main class="mainContainer">
		<header class="headerMain">
			<div class="botoesHeaderMainCard">
				<button><span class="material-symbols-outlined">arrow_back_ios</span></button>
				<button><span class="material-symbols-outlined">arrow_forward_ios</span></button>
			</div>

			<div class="profilePictureCard">
				<img class="profilePicture" alt="profilePicture" src="../assets/imagens/profilePicture.jpg">
			</div>
		</header>

		<div class="mainCardContent">
			
			<BoaTardeConteudo></BoaTardeConteudo>
			
			<Sugestoes :type="Types.Recents"></Sugestoes>
			<Sugestoes :type="Types.Podcast"></Sugestoes>
			<Sugestoes :type="Types.Mixes"></Sugestoes>
			
		</div>
	</main>

</template>

<script>

import {defineComponent} from "vue";
import BoaTardeConteudo from "@/components/BoaTardeConteudo.vue";
import {Types} from "@/assets/Utils";
import Sugestoes from "@/components/Sugestoes.vue";

export default defineComponent({
	name: "MainCard",
	computed: {
		Types() {
			return Types
		}
	},
	components: {Sugestoes, BoaTardeConteudo},

	setup() {

		return {
			
		}
	}
})

</script>

<style scoped>

.mainContainer {
	background: var(--mainCardBackground);
	border-radius: var(--cardsBorderRadius);
	color: white;
	overflow: auto;
	grid-area: main;
}

.headerMain {
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 20px;
	background: hsla(0, 0%, 22%, 0.98);
	position: sticky;
	top: 0;
}

.botoesHeaderMainCard > button {
	background: var(--botaoMainCardBackground);
	color: var(--textSecondary);
	border: none;
	width: 30px;
	height: 30px;
	border-radius: 15px;
	text-align: center;
	padding-left: 5px;
	margin-right: 10px;
}

.botoesHeaderMainCard > button:hover {
	color: var(--textPrimary);
	transition: 200ms;
	cursor: pointer;
}

.material-symbols-outlined {
	font-size: 20px;
}

.profilePicture {
	width: 30px;
	height: 30px;
	border: 2px solid var(--sideBardBackground);
	border-radius: 18px;
}

.profilePicture:hover {
	opacity: 80%;
	transition: 200ms;
	cursor: pointer;
}

</style>