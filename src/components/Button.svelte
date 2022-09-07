<script>
	import { Link } from "svelte-routing";

	export let to;
	export let color = 'white-yellow';
	export let callback = function () {};

	let mainColor = `var(--color-${color})`
	let backgroundColor = `var(--color-${color}-transparent)`
</script>


<Link to="{to}">
	<button style="--main-color: {mainColor}; --background-color: {backgroundColor}" on:click={callback}>
		<slot>
		</slot>
	</button>
</Link>


<style>
	button, input {
		padding: 1rem 2rem;
		border-radius: var(--default-radius);
		cursor: pointer;
		display: inline-block;
		color: var(--color-white-yellow);

		background: var(--background-color); 
		border: 1px solid var(--main-color);
		box-shadow: 0px 1px 4px var(--background-color), inset 0px 4px 4px rgba(36, 36, 36, 0.2);

		transition: background 0.3s, box-shadow 0.3s, color 0.3s;
	}

	button:hover, input:hover {
		background: var(--main-color);
		color: var(--color-black);
		box-shadow: 0px 4px 8px var(--background-color), inset 0px 4px 4px rgba(36, 36, 36, 0.2);
	}
</style>