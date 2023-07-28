<template>
	
	<MainCard></MainCard>

	<AsideBar></AsideBar>

	<Footer></Footer>
</template>

<script>
import {defineComponent} from "vue";
import AsideBar from "@/components/AsideBar.vue";
import MainCard from "@/components/MainCard.vue";
import Footer from "@/components/Footer.vue";


export default defineComponent({
	components: {Footer, MainCard, AsideBar},

	setup() {

	}
})

</script>

<style>

@import "../assets/styleGeral.css";

</style>