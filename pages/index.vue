<template>
	<div class="background">
		<h1 class="header">Menu</h1>
		<div class="buttons">
			<button class="button" @click="$router.push(`/Game`)">Start</button>
			<button class="button" @click="$router.push(`/LeaderBoard`)">Leader Board</button>
			<button class="button" @click="exit()">Exit</button>
		</div>
	</div>
</template>

<script setup>
async function exit() {
	await $post("/exit");
	// Não funcionando? Culpa do servidor?
} 
</script>

<style>
@keyframes rainbow {
	0% {
		color: #f5f5f5;
	}

	25% {
		color: #36bbf5;
	}

	50% {
		color: #00ffaa;
	}

	75% {
		color: #c300ff;
	}

	100% {
		color: #f5f5f5;
	}
}

.background {
	width: 100vw;
	height: 100vh;

	background-origin: content-box;
	background-image: url("~/assets/space.png");

	z-index: 0;
	overflow: hidden;
	position: relative;

	display: flex;
	align-items: center;
	flex-direction: column;
	justify-content: center;
}

.header {
	text-align: center;
	font-size: xxxxxx-large;
	animation: rainbow 4s linear infinite;
	font-family: 'Courier New', Courier, monospace;
}

.buttons {
	display: flex;
	align-items: center;
	flex-direction: column;
}

.button {
	width: 12rem;
	height: 5rem;
	margin: 0.5rem;
	color: #36bbf5;
	font-size: medium;
	border-radius: 1rem;
	background: #f5f5f5;
	font-family: 'Courier New', Courier, monospace;
}

.button:hover {
	color: #f5f5f5;
	background-color: #36bbf5;
	border: 0.2rem solid #36bbf5;
}</style>