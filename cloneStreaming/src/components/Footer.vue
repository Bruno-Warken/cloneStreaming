<template>
	<footer class="footer">
		<div class="footerLeftGroup">

			<img class="cover" alt="footerAlbumCover"
			     src="https://upload.wikimedia.org/wikipedia/pt/4/4f/Evermore_-_Taylor_Swift.png">

			<div class="footerText">
				<p class="titulo">marjorie</p>
				<p class="subTitulo">Taylor Swift</p>
			</div>

			<div class="iconsLeft">
				<span class="material-symbols-outlined left">favorite</span>
				<span class="material-symbols-outlined left">picture_in_picture_alt</span>
			</div>
		</div>

		<div class="footerMiddleGroup">

			<div class="iconsMiddle">
				<span class="material-symbols-outlined middle smallSize shuffle">shuffle</span>
				<span class="material-symbols-outlined middle midSize">skip_previous</span>
				<span class="material-symbols-outlined middle bigSize">play_circle</span>
				<span class="material-symbols-outlined middle midSize">skip_next</span>
				<span class="material-symbols-outlined middle smallSize">repeat</span>
			</div>

			<div class="musicProgress">
				<p class="musicTime">2:51</p>
				<progress id="progressMusic" value="68" max="100"></progress>
				<p class="musicTime">4:19</p>
			</div>

		</div>

		<div class="footerRightGroup">

			<div class="iconsRight">
				<span class="material-symbols-outlined right">slideshow</span>
				<span class="material-symbols-outlined right">mic_external_on</span>
				<span class="material-symbols-outlined right">menu</span>
				<span class="material-symbols-outlined right">cast</span>
				<span class="material-symbols-outlined right">volume_down_alt</span>
				<progress id="progressVolume" value="36" max="100"></progress>
				<span class="material-symbols-outlined right">open_in_full</span>
			</div>

		</div>

	</footer>
</template>

<script>

import {defineComponent} from "vue";

export default defineComponent({
	name: "Footer",

	setup() {
		return {}
	}
})

</script>

<style scoped>

.material-symbols-outlined {
	color: var(--textSecondary);
}

.material-symbols-outlined:hover {
	color: var(--textPrimary);
	transition: 200ms;
	cursor: pointer;
}

.footer {
	grid-area: ft;
	display: flex;
	align-items: center;
	padding: 10px;
}

.footerLeftGroup {
	display: flex;
	gap: 20px;
	width: 30%;
}

.cover {
	width: 60px;
	border-radius: 8px;
}

.footerText {
	display: flex;
	flex-direction: column;
	gap: 8px;
	justify-content: center;
}

.titulo {
	font-size: 14px;
	color: var(--textPrimary);
}

.titulo:hover {
	cursor: pointer;
	text-decoration: underline;
}

.subTitulo {
	font-size: 12px;
	color: var(--textSecondary);
}

.subTitulo:hover {
	color: var(--textPrimary);
	cursor: pointer;
	text-decoration: underline;
}

.left {
	font-size: 22px;
}

.iconsLeft {
	display: flex;
	gap: 10px;
	align-items: center;
}

.footerMiddleGroup {
	padding: 10px;
	text-align: center;
	width: 40%;
}

.iconsMiddle {
	display: flex;
	gap: 20px;
	justify-content: center;
	align-items: center;
}

.smallSize {
	font-size: 22px;
}

.midSize {
	font-size: 30px;
}

.bigSize {
	font-size: 46px;
}

.shuffle {
	color: hsl(120, 100%, 35%);
}

.shuffle:hover {
	color: hsl(120, 100%, 40%);
}

#progressMusic {
	width: 90%;
	height: 4px;
	background: var(--textPrimary);
}

#progressVolume {
	width: 20%;
	height: 4px;
	background: var(--textPrimary);
}

progress::-webkit-progress-value {
	background: var(--textPrimary);
}

.musicProgress {
	display: flex;
	gap: 10px;
	align-items: center;
}

.musicTime {
	color: var(--textPrimary);
	font-size: 12px;
}

.footerRightGroup {
	width: 30%;
}

.iconsRight {
	display: flex;
	justify-content: flex-end;
	align-items: center;
	gap: 10px;
}

.right {
	font-size: 22px;
}


</style>