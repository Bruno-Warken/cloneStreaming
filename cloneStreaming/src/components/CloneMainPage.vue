<template>
	<main class="mainContainer">
		<header class="headerMain">

		</header>
	</main>
	
	<AsideBar></AsideBar>

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
import AsideBar from "@/components/AsideBar.vue";


export default defineComponent({
	components: {AsideBar},

	setup() {

		return {
			
		}
	}
})

</script>


<style>

@import "../assets/styleGeral.css";

.mainContainer {
	background: var(--mainCardBackground);
	border-radius: var(--cardsBorderRadius);
	color: white;
	grid-area: main;
}

/*Estilização do footer*/

.footer {
	color: white;
	grid-area: ft;
}

</style>