<script>
	import {Link} from "svelte-routing";
</script>

<nav>
	<Link to='/'>
		<a class="brand" href="#">Passtock</a>
	</Link>

	<div class="menu">
		<slot class="menu">
			
		</slot>
	</div>
</nav>

<style>
	nav {
		margin: 0px 5% 2rem 5%;
		padding: 1rem calc(var(--horizontal-page-padding) - 5%);
		margin-bottom: 2rem;

		display: flex;
		align-items: center;
		justify-content: space-between;

		border-radius: 0px 0px 10px 10px;
		box-shadow: 0px 1px 4px 0px var(--color-white-yellow-transparent);
		background: rgba(255, 255, 255, 0.05);
	}

	.brand {
		font-weight: 700;
		font-size: 1.2rem;
		filter: drop-shadow(0px 0px 4px var(--color-white-yellow-transparent));
		transition: filter 0.3s;
	}
	.brand:hover {
		filter: drop-shadow(0px 0px 4px var(--color-purple-transparent));
	}

	.menu {
		display: flex;
		align-items: center;
	}

	.menu a {

	}
</style>