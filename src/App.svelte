<script>
	import { onMount } from 'svelte';
	import './TailwindStyles.svelte';
	
	const message = 'Learn Svelte';

	let flickityReady = false;
	let mounted = false;
	
	onMount(() => {
		// The payment-form is ready.
		mounted = true;
		if (flickityReady) {
			loadFlickityElements();
		}
	});

	function flickityLoaded() {
		// The external Flickity javascript is ready.
		flickityReady = true;
		if (mounted) {
			loadFlickityElements();
		}
	}

	function loadFlickityElements() {
		// Time for Flickity to do its magic.
		console.log("Init Flickity")
	}
</script>

<svelte:head>
<!-- JavaScript -->
<script src="https://unpkg.com/flickity@2/dist/flickity.pkgd.min.js" on:load={flickityLoaded}></script>
<link rel="stylesheet" href="https://unpkg.com/flickity@2/dist/flickity.min.css">
</svelte:head>

<style>
	.App-logo {
		animation: App-logo-scale infinite 1.6s ease-in-out alternate;
	}
	@keyframes App-logo-scale {
		from {
			transform: scale(1);
		}
		to {
			transform: scale(1.06);
		}
	}
</style>

<div class="text-center font-serif">
	<header class="bg-gray-100 h-screen flex justify-center items-center flex-col text-3xl">
		<img src="/logo.svg" class="App-logo pointer-events-none m-4 h-64" alt="logo" />
		<p>
			Edit <code>src/App.svelte</code> and save to reload.
		</p>
		<a
			class="text-orange-500"
			href="https://svelte.dev"
			target="_blank"
			rel="noopener noreferrer"
		>
			{message}
		</a>
	</header>
</div>
