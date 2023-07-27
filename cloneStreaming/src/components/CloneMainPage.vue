<template>
	<main class="mainContainer">
		<header class="headerMain">

		</header>
	</main>

	<aside class="sideBar">
		<div class="sideTopMenu">
			<ul class="ulSideTopMenu">
				<li><span class="material-symbols-outlined">home</span>Início</li>
				<li><span class="material-symbols-outlined">search</span> Buscar</li>
			</ul>
		</div>

		<div class="sideBottomMenu">
			<div class="containerBottomMenu">
				<header class="headerSideMenu">
					<h2 class="suaBiblioteca"><span class="material-symbols-outlined">tune</span>Sua Biblioteca</h2>
					<h2><span class="material-symbols-outlined">add</span></h2>
					<h2><span class="material-symbols-outlined">arrow_forward</span></h2>
				</header>

				<div class="botoesSide">
					<div class="scrollContainer" ref="scrollContainerRef">
						<button>Playlists</button>
						<button>Artistas</button>
						<button>Álbuns</button>
						<button>Podcasts & Shows</button>
					</div>
					<button @click="scrollLeft" v-show="canScrollLeft" class="scrollButtonLeft">←</button>
					<button @click="scrollRight" v-show="canScrollRight" class="scrollButtonRight">→</button>
				</div>

				<div class="recentes">
					<span class="material-symbols-outlined">search</span>
					<select>
						<option>Recentes</option>
						<option>Adicionados Recentemente</option>
						<option>Alfabético</option>
						<option>Criador</option>
					</select>
				</div>
			</div>

			<RecentesConteudo></RecentesConteudo>
			
		</div>

	</aside>

	<footer class="footer">
		<div class="footerLeftGroup">

		</div>

		<div class="footerMiddleGroup">

		</div>

		<div class="footerRightGroup">

		</div>
	</footer>
</template>

<script>
import {defineComponent, onMounted, ref} from "vue";
import RecentesConteudo from "@/components/RecentesConteudo.vue";

export default defineComponent({
	components: {RecentesConteudo},

	setup() {

		const scrollContainerRef = ref(null);
		const canScrollRight = ref(true);
		const canScrollLeft = ref(false);

		function scroll(left) {

			const scrollContainer = scrollContainerRef.value;
			const ammount = 30;

			if (scrollContainer) {
				if (left) {
					scrollContainer.scrollLeft -= ammount;
				} else {
					scrollContainer.scrollLeft += ammount;
				}
				updateScrollButtonVisibility();
			}
		}

		function scrollLeft() {
			scroll(true);
		}

		function scrollRight() {
			scroll(false);
		}

		function updateScrollButtonVisibility() {
			const scrollContainer = scrollContainerRef.value;

			canScrollLeft.value = scrollContainer.scrollLeft > 0;
			canScrollRight.value = scrollContainer.scrollLeft < scrollContainer.scrollWidth - scrollContainer.clientWidth;
		}

		return {
			scrollContainerRef,
			canScrollLeft,
			canScrollRight,
			scrollLeft,
			scrollRight,
		}
	}
})

</script>

<!--suppress CssUnknownTarget -->
<style>

@import url('https://fonts.googleapis.com/css2?family=Figtree:wght@300;400;500;600;700&display=swap');
@import "../assets/styleGeral.css";

.mainContainer {
	background: var(--mainCardBackground);
	border-radius: var(--cardsBorderRadius);
	color: white;
	grid-area: main;
}

/*Estilização geral da sidebar*/

.sideBar {
	grid-area: side;
	display: flex;
	flex-direction: column;
	gap: 8px;
	border-radius: var(--cardsBorderRadius);
}

.material-symbols-outlined {
	font-size: 30px;
	font-weight: 300;
}

/*Estilização do container superior da sidebar*/

.sideTopMenu {
	height: 15%;
	min-height: 120px;
	background: var(--sideBardBackground);
	border-radius: var(--cardsBorderRadius);
	color: var(--textSecondary);
}

ul {
	list-style: none;
	padding: 12px;
}

li {
	display: flex;
	align-items: center;
	margin: 2px;
	gap: 20px;
	padding: 8px;
	flex-wrap: wrap;
	font-weight: 700;
}

:is(li, h2):hover {
	cursor: pointer;
	color: var(--textPrimary);
	transition: 200ms;
}

/*Estilização do container inferior da sidebar*/

.sideBottomMenu {
	height: 85%;
	background: var(--sideBardBackground);
	border-radius: var(--cardsBorderRadius);
}

.containerBottomMenu {
	display: flex;
	flex-direction: column;
	gap: 16px;
}

.headerSideMenu {
	display: flex;
	justify-content: space-evenly;
	margin-top: 10px;
}

h2 {
	color: var(--textSecondary);
	font-size: 16px;
}

.suaBiblioteca {
	display: flex;
	align-items: center;
	gap: 4px;
}

.botoesSide {
	position: relative;
}

.scrollContainer {
	margin-left: 10px;
	display: flex;
	gap: 5px;
	scroll-behavior: smooth;
	overflow: hidden;
}

.scrollContainer > button {
	white-space: nowrap;
	padding: 8px 12px;
	font-size: 12px;
	font-weight: 600;
	border-radius: 30px;
	background: var(--buttonBackground);
	color: var(--textPrimary);
	border: none;
}

.scrollContainer > button:hover {
	cursor: pointer;
	background: var(--buttonBackgroundHover);
	transition: 200ms;
}

.scrollButtonLeft {
	width: 30px;
	height: 30px;
	border-radius: 15px;
	background: var(--buttonBackgroundHover);
	color: var(--textSecondary);
	border: none;
	position: absolute;
	top: 0;
	left: 2%;
}

.scrollButtonLeft:hover {
	cursor: pointer;
	color: var(--textPrimary);
	transition: 200ms;
}

.scrollButtonRight {
	width: 30px;
	height: 30px;
	border-radius: 15px;
	background: var(--buttonBackgroundHover);
	color: var(--textSecondary);
	border: none;
	position: absolute;
	top: 0;
	left: 87%;
}

.scrollButtonRight:hover {
	cursor: pointer;
	color: var(--textPrimary);
	transition: 200ms;
}

.recentes {
	display: flex;
	justify-content: space-between;
	margin: 0 10px;
	color: var(--textSecondary);
}

.recentes .material-symbols-outlined:hover {
	cursor: pointer;
	color: var(--textPrimary);
	transition: 200ms;
}

select {
	width: 90px;
	background: none;
	border: none;
	color: var(--textPrimary);
}

select:focus {
	outline: none;
}

select > option {
	background: var(--selectBackground);
}

/*Estilização do footer*/

.footer {
	color: white;
	grid-area: ft;
}

</style>