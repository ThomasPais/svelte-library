<script lang="ts">
	export let open = false;

	function setOpen(value: boolean) {
		open = value;
	}
</script>

<button
	type="button"
	aria-controls="navbar"
	aria-expanded={open}
	aria-label={open ? 'Close navigation menu' : 'Open navigation menu'}
	class="hamburger-button"
	on:click={() => setOpen(!open)}
>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		viewBox="0 0 100 100"
		width="var(--size, 1.5rem)"
		fill="currentColor"
	>
		<rect class="top" width="80" height="10" x="10" y="25" rx="5"> </rect>
		<rect class="middle" width="80" height="10" x="10" y="45" rx="5"> </rect>
		<rect class="bottom" width="80" height="10" x="10" y="65" rx="5"> </rect>
	</svg>
</button>

<style>
	.hamburger-button {
		width: var(--size, 1.5rem);
		height: var(--size, 1.5rem);
		background: none;
		border: none;
		color: var(--color, black);
		cursor: pointer;
		padding: 0;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.hamburger-button rect {
		transform-origin: center;
		transition:
			y 250ms ease 250ms,
			rotate 250ms ease,
			opacity 0ms 250ms;
	}

	.hamburger-button[aria-expanded='true'] rect {
		transition:
			y 250ms ease,
			rotate 250ms ease 250ms,
			opacity 0ms 250ms;
	}

	.hamburger-button[aria-expanded='true'] :is(.top, .bottom) {
		y: 45px;
	}

	.hamburger-button[aria-expanded='true'] .top {
		rotate: 45deg;
	}

	.hamburger-button[aria-expanded='true'] .middle {
		opacity: 0;
	}

	.hamburger-button[aria-expanded='true'] .bottom {
		rotate: -45deg;
	}
</style>
