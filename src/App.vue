<template>
	<router-view v-slot="{ Component }">
		<transition name="fade" mode="out-in">
			<component :is="Component" />
		</transition>
	</router-view>
</template>

<script>
	export default {
		mounted(){
			console.log('init Dice Game • V 0.1');
		},
		head: {
			title: {
				inner: '',
				separator: '🎲',
				complement : 'Dice Games',
			},
			link: [
				{ rel: 'manifest', href: "./manifest.webmanifest" },
				{ rel: 'icon', href: "data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🎲</text></svg>" }
			]
		}
	}
</script>

<style lang="less">
	*{
		box-sizing: border-box;
		padding: 0;
		margin: 0;
		user-select: none;
	}
	body{
		background-color: #2b3037;
		overflow: hidden;
		height: 100vh;
		width: 100vw;
	}
	button{
		cursor: pointer;
	}

	// Fade

		.fade-enter-active,
		.fade-leave-active{
			transition: opacity .5s ease;
		}

		.fade-enter-from,
		.fade-leave-to{
			opacity: 0;
		}

		.fade-enter-to,
		.fade-leave-from{
			opacity: 1;
		}

</style>