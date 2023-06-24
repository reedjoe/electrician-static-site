<script>
	import { page } from '$app/stores';
    import CoverPhoto from '../components/CoverPhoto.svelte';
    import Footer from '../components/Footer.svelte';
	import Nav from '../components/Nav.svelte';

	import Header from './Header.svelte';
	import './styles.css';
</script>

<div class="app">
	<!-- <Header /> -->
	<Nav />

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

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
