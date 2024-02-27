<script lang="ts">
	import '../app.css';
	import { tick } from 'svelte';
	import { Confetti } from 'svelte-confetti';

	let active = false;
	async function showConfetti() {
		active = false;
		await tick();
		active = true;
	}
</script>

<!-- HEADER -->

<nav>
	<div class="flex justify-between text-lg m-5 lg:m-10 border-b-2">
		<a href="/about" class="hover:bg-sky-700 transition ease-in-out">ABOUT</a>
		<a href="/portfolio" class="hover:bg-sky-700 transition ease-in-out">PORTFOLIO</a>
		<a href="/contact" class="hover:bg-sky-700 transition ease-in-out">CONTACT</a>
	</div>
</nav>

<div class=" w-100 flex justify-center">
	<h1>
		<div class="text-6xl lg:text-9xl font-bold">
			<a href="/" class="hover:bg-sky-700 transition ease-in-out" on:click={showConfetti}>
				ANITA HAGHIGHI
			</a>
			{#if active}
				<div class="flex justify-center"><Confetti /></div>
			{/if}
		</div>
	</h1>
</div>

<!-- MAIN CONTENT -->
<div class="flex justify-center mt-7">
	<slot />
</div>

<!-- FOOTER -->
<style>
	nav {
		font-family: Anton;
	}
	h1 {
		font-family: Anton;
	}

	a {
	}
</style>
