<script lang="ts">
	import { page } from '$app/stores';
    import CoverPhoto from '../components/CoverPhoto.svelte';
    import Footer from '../components/Footer.svelte';
	import Nav from '../components/Nav.svelte';

	import './styles.css';
</script>

<div class="app">
	<Nav />

	<!-- TODO this is crap don't do this -->
	{#if $page.url.pathname === '/'}
		<CoverPhoto />
	{/if}

	<main>
		<slot />
	</main>

	<Footer />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 64rem;
		margin: 0 auto;
		box-sizing: border-box;
		margin-top: 3em;
	}
</style>
