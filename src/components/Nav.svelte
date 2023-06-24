<script lang="ts">
    import { beforeNavigate } from "$app/navigation";
	import { page } from "$app/stores";
	import logo from "$lib/images/jarvis_electrical_logo.jpg";

	let mobileNavElem: HTMLElement;

	beforeNavigate(()=>{
		mobileNavElem.style.display = "none";
	});

	function toggleMobileNav() {
		mobileNavElem.style.display =
			mobileNavElem.style.display === "none" ||
			mobileNavElem.style.display === ""
				? "initial"
				: "none";
	}
</script>

<header>
	<div class="left-corner">
		<div class="mobile-nav-toggle" on:click={toggleMobileNav}>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				width="48"
				height="48"
				viewBox="0 0 72 72"
			>
				<g id="line">
					<line
						x1="16"
						x2="56"
						y1="26"
						y2="26"
						fill="none"
						stroke="#ffffff"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-miterlimit="10"
						stroke-width="2"
					/>
					<line
						x1="16"
						x2="56"
						y1="36"
						y2="36"
						fill="none"
						stroke="#ffffff"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-miterlimit="10"
						stroke-width="2"
					/>
					<line
						x1="16"
						x2="56"
						y1="46"
						y2="46"
						fill="none"
						stroke="#ffffff"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-miterlimit="10"
						stroke-width="2"
					/>
				</g>
			</svg>
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
			<a href="tel:+1234567891">01603 777888</a>
		</address>
	</div>

	<nav class="mobile-nav" bind:this={mobileNavElem}>
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

	.mobile-nav {
		display: none;
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
