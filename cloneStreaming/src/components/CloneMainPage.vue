<template>
	
	<MainCard></MainCard>

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
import {defineComponent} from "vue";
import AsideBar from "@/components/AsideBar.vue";
import MainCard from "@/components/MainCard.vue";


export default defineComponent({
	components: {MainCard, AsideBar},

	setup() {

	}
})

</script>

<style>

@import "../assets/styleGeral.css";

/*Estilização do footer*/

.footer {
	color: white;
	grid-area: ft;
}

</style>