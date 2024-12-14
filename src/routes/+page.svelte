<script lang="ts">
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcomeFallback from '$lib/images/svelte-welcome.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<h1>Birthday movie counter</h1>
<section>
	<div class="team red">
team red
	</div>
	<div class="team yellow">
team yellow
	</div>
	<Counter />
</section>

<style>
	section {
		display: flex;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}
	team {
		flex-grow: 1;
	}

	red {
		background-color: red;
	}

	yellow {
		background-color: yellow;
	}

	h1 {
		width: 100%;
	}
</style>
