<script lang="ts">
	import Hamburger from '$lib/components/hamburger/hamburger.svelte';
	import GithubIcon from '~icons/mdi/github';
	import LinkedinIcon from '~icons/mdi/linkedin';
	import MagnifyIcon from '~icons/mdi/magnify';
	import TwitterIcon from '~icons/mdi/twitter';

	let open = false;

	function setOpen(value: boolean) {
		open = value;
	}
</script>

<header>
	<div class="container header-container">
		<div class="brand"><a href="/">Thomas Païs</a></div>
		<div class="navigation-container">
			<nav class="navbar" aria-hidden={!open}>
				<ul class="navbar-links">
					<li class="navbar-link"><a href="/" on:click={() => setOpen(false)}> Home </a></li>
					<li class="navbar-link"><a href="/" on:click={() => setOpen(false)}> About </a></li>
					<li class="navbar-link"><a href="/" on:click={() => setOpen(false)}> Projects </a></li>
					<li class="navbar-link"><a href="/" on:click={() => setOpen(false)}> Articles </a></li>
				</ul>
			</nav>

			<ul class="socials">
				<li class="social">
					<a href="/" class="social-link"><TwitterIcon /> </a>
				</li>
				<li class="social">
					<a href="/" class="social-link"> <GithubIcon /> </a>
				</li>
				<li class="social">
					<a href="/" class="social-link"> <LinkedinIcon /></a>
				</li>
			</ul>
			<div class="search"><MagnifyIcon /></div>
			<div class="mobile-navigation-button">
				<Hamburger bind:open --color="white" --size="1.5rem" />
			</div>
		</div>
	</div>
</header>

<style>
	header {
		height: 64px;
		margin: 8px 8px 0px 8px;
		border-radius: 8px;
		background-color: var(--surface-color);
	}

	.header-container {
		height: 100%;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.brand {
		font-size: 1.5rem;
	}

	.navigation-container {
		display: flex;
		align-items: center;
	}

	.navbar {
		visibility: hidden;
		position: fixed;
		inset: 0 0 0 0;
		transition:
			500ms opacity ease,
			500ms visibility linear;
		opacity: 0;
		background-color: var(--surface-color);
	}

	.navbar[aria-hidden='false'] {
		visibility: visible;
		opacity: 1;
	}

	.navbar-links {
		padding: 64px 1rem 64px 1rem;
		margin: 0;
	}

	.navbar-link {
		height: 4rem;
		font-size: 2rem;
	}

	.socials {
		padding-left: 0;
		display: flex;
		justify-content: space-between;
	}

	.social {
		width: 1.5rem;
		height: 1.5rem;
		margin-inline: 8px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.search {
		width: 1.5rem;
		height: 1.5rem;
		margin-inline: 8px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.mobile-navigation-button {
		width: 1.5rem;
		height: 1.5rem;
		margin-left: 8px;
		z-index: 10;
	}

	@media only screen and (min-width: 768px) {
		.navbar {
			visibility: visible;
			position: relative;
			opacity: 1;
			transition: none;
			background: none;
			display: flex;
		}

		.navbar-links {
			padding: 64px 1rem 64px 1rem;
			margin: 0;
			display: flex;
		}

		.navbar-link {
			height: auto;
			font-size: 1rem;
			padding-inline: 8px;
		}

		.navbar-links li:last-child {
			border-right: 2px solid gray;
		}

		.mobile-navigation-button {
			display: none;
		}
	}
</style>
