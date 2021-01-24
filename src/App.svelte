<script lang="ts">
	import Stage from "./components/Stage.svelte";
	import Artists from "./components/Artists.svelte";
	import { onMount } from "svelte";
	let y;
	let artists;
	let contact;

	onMount(() => {
		artists = document.querySelector("#artists");
		contact = document.querySelector("#contact");
	});
</script>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: Roboto, sans-serif;
	}

	:global(section) {
		height: 100vh;
		display: flex;
	}

	main {
		margin: 0;
		padding: 0;
	}

	nav {
		display: flex;
		position: absolute;
		align-items: flex-end;
		flex-direction: column;
		top: 0;
		right: 0;
		padding: 60px;
	}

	nav span::after {
		content: "";
		position: absolute;
		width: 100%;
		background-color: #e14900;
		height: 2px;
		bottom: -2px;
		left: 0;
		transform: scaleX(0);
		transform-origin: bottom right;
		transition: transform 0.4s cubic-bezier(0.86, 0, 0.07, 1);
	}

	nav span:hover::after {
		transform: scaleX(1);
		transform-origin: bottom left;
	}

	nav span {
		margin-bottom: 30px;
		font-size: larger;
		color: #e14900;
		position: relative;
		text-decoration: none;
	}
</style>

<svelte:window bind:scrollY={y} />
<header>
	<nav>
		<span
			on:click={() => window.scroll({
					top: 0,
					behavior: 'smooth',
				})}>exhibition</span>
		<span
			on:click={() => artists.scrollIntoView({
					behavior: 'smooth',
				})}>artists</span>
		<span
			on:click={() => contact.scrollIntoView({
					behavior: 'smooth',
				})}>contact</span>
	</nav>
	<Stage />
</header>
<main>
	<Artists />
</main>
