<script lang="ts">
    import { beforeNavigate } from "$app/navigation";
	import { page } from "$app/stores";
	import logo from "$lib/images/jarvis_electrical_logo.jpg";
    import hamburger from "$lib/icons/hamburger.svg";
	import { phoneNumber } from "$lib/constants";

	let mobileNavElem: HTMLElement;
	let isMobileNavExpanded = false;

	beforeNavigate(() => {
		isMobileNavExpanded = false;
		document.body.style.overflow = 'initial';
	});

	function handleMobileNavKeydown(event: KeyboardEvent) {
		if (event.key === ' ' || event.key === 'Enter') {
			event.preventDefault();
			toggleMobileNav();
		}
	}

	function toggleMobileNav() {
		isMobileNavExpanded = !isMobileNavExpanded;
		document.body.style.overflow = isMobileNavExpanded ? 'hidden' : 'initial';
	}
</script>

<header>
	<div class="left-corner">
		<div
			class="mobile-nav-toggle"
			on:click={toggleMobileNav}
			on:keydown={handleMobileNavKeydown}
			role="button"
			tabindex="0">
			<img class="hamburger" src={hamburger} alt="Toggle navigation menu" />
		</div>
	
		<div class="logo-wrapper">
			<img class="logo" src={logo} alt="Jarvis electrical services logo" />
		</div>
	</div>

	<nav class="desktop-nav">
		<ul>
			<li aria-current={$page.url.pathname === "/" ? "page" : undefined}>
				<a href="/">Home</a>
			</li>
			<li
				aria-current={$page.url.pathname === "/about"
					? "page"
					: undefined}
			>
				<a href="/about">About</a>
			</li>
			<li
				aria-current={$page.url.pathname === "/services"
					? "page"
					: undefined}
			>
				<a href="/services">Services</a>
			</li>
		</ul>
	</nav>

	<div class="right-corner">
		<address>
			<a href="tel:+{phoneNumber}">{phoneNumber}</a>
		</address>
	</div>

	<nav class="mobile-nav {isMobileNavExpanded ? 'visible' : 'hidden'}" bind:this={mobileNavElem}>
		<ul>
			<li aria-current={$page.url.pathname === "/" ? "page" : undefined}>
				<a href="/">Home</a>
			</li>
			<li
				aria-current={$page.url.pathname === "/about"
					? "page"
					: undefined}
			>
				<a href="/about">About</a>
			</li>
			<li
				aria-current={$page.url.pathname === "/services"
					? "page"
					: undefined}
			>
				<a href="/services">Services</a>
			</li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 3em;
		top: 0;
		position: fixed;
		background-color: #353839f6;
		z-index: 999;
	}

	.left-corner {
		display: flex;
	}

	.logo {
		height: 48px;
	}

	.right-corner {
		display: flex;
		justify-content: center;
		background-color: var(--color-theme-1);
		padding-right: 10px;
		padding-left: 10px;
	}

	.right-corner address {
		display: flex;
		flex-direction: row;
		gap: 5px;
		align-items: center;
		justify-content: center;
	}

	.right-corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
		color: var(--color-text);
	}

	.mobile-nav-toggle:hover {
		cursor: pointer;
		background-color: #dfdfdfc5;
	}

	.desktop-nav {
		position: absolute;
		top: 0;
		left: 50%;
		transform: translate(-50%, 0%);

		display: none;
		justify-content: center;
	}

	.desktop-nav ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
	}

	.desktop-nav li {
		position: relative;
		height: 100%;
	}

	.desktop-nav li[aria-current="page"]::before {
		--size: 6px;
		content: "";
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: rgba(244, 244, 244, 0.876);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	nav a:hover {
		color: var(--color-theme-1);
	}

	.mobile-nav {
		position: absolute;
		top: 48px;
		width: 250px;
		height: 100vh;
		background-color: #353839f6;
		transform: translateX(-100%);
    	-webkit-transform: translateX(-100%);
	}

	.hidden {
		animation: slide-out 0.35s forwards;
		-webkit-animation: slide-out 0.35s forwards;
	}

	.visible {
		animation: slide-in 0.4s forwards;
    	-webkit-animation: slide-in 0.4s forwards;
	}

	@keyframes slide-in {
		100% { transform: translateX(0%); }
	}

	@-webkit-keyframes slide-in {
		100% { -webkit-transform: translateX(0%); }
	}
		
	@keyframes slide-out {
		0% { transform: translateX(0%); }
		100% { transform: translateX(-100%); }
	}

	@-webkit-keyframes slide-out {
		0% { -webkit-transform: translateX(0%); }
		100% { -webkit-transform: translateX(-100%); }
	}

	.mobile-nav ul {
		display: flex;
		flex-direction: column;
		gap: 30px;
		justify-content: center;
		align-items: center;
		list-style: none;
		padding-left: 0;
		padding-top: 20px;
	}

	.mobile-nav li[aria-current="page"] a {
		color: var(--color-theme-1);
	}

	@media screen and (min-width: 600px) {
		.mobile-nav-toggle {
			display: none;
		}

		.desktop-nav {
			display: flex;
		}
	}
</style>
