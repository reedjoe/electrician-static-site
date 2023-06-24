<script lang="ts">
	import profile_photo from "$lib/images/emmanuel-ikwuegbu-zWOgsj3j0wA-unsplash.jpg";
	import rccb_photo from "$lib/images/markus-spiske-kK7uPfb2YWU-unsplash.jpg";
</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About" />
</svelte:head>

<div class="text-column">
	<h1>About us</h1>

	<p>
		Here you can put some info about yourself. e.g. been working as an electrician for x years. Add whatever info you feel is useful for people to know about you here. Also, imagine that the picture below is of you - I couldn't find any particularly <i>professional</i> photos of you on my phone.
	</p>

	<img class="profile_photo" src={profile_photo} alt="Haydon Jarvis" />

	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

	
	<h1>Experience</h1>

	<div class="experience-wrapper">
		<img class="rccb_photo" src={rccb_photo} alt="RCCB" />
		<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
		<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
	</div>
	
	<h1>Qualifications</h1>

	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
</div>

<style>
	.profile_photo {
		margin: auto;
		max-width: 300px;
	}

	.experience-wrapper {
		display: grid;
		grid-template-columns: 150px 1fr;
		gap: 25px;
	}

	.experience-wrapper > p:last-of-type {
		grid-column: 1 / -1;
	}

	.rccb_photo {
		max-width: 150px;
	}

	@media screen and (min-width: 600px) {
		.profile_photo {
			max-width: 500px;
		}

		.experience-wrapper {
			display: grid;
			grid-template-columns: 350px 1fr;
			gap: 40px;
		}

		.rccb_photo {
			max-width: 350px;
		}
	}
</style>
