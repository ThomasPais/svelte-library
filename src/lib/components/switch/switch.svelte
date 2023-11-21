<script lang="ts">
	export let checked = false;

	function setChecked(value: boolean) {
		checked = value;
	}
</script>

<button type="button" role="switch" aria-checked={checked} on:click={() => setChecked(!checked)}>
	<span class="slider"> </span>
</button>

<style>
	button {
		font-size: var(--switch-size, 1rem);
		position: relative;
		width: 3em;
		height: 1.5em;
		border: none;
		border-radius: 1.5em;
		background-color: var(--switch-primary-color, #28292c);
		cursor: pointer;
		transition: background-color 300ms ease;
	}

	.slider {
		position: absolute;
		width: 1.25em;
		height: 1.25em;
		left: 0.125em;
		top: 0.125em;
		background-color: var(--switch-secondary-color, #d8dbe0);
		border-radius: 100%;
		transition:
			left 300ms ease,
			background-color 300ms ease;
	}

	button[aria-checked='true'] {
		background-color: var(--switch-secondary-color, #d8dbe0);
	}

	button[aria-checked='true'] .slider {
		left: 1.625em;
		background-color: var(--switch-primary-color, #28292c);
	}
</style>
