<script lang="ts">
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcomeFallback from '$lib/images/svelte-welcome.png';

	let scoreTeamRed = 0;
	let scoreTeamYellow = 0;

	function addPointsToRed(points) {
		scoreTeamRed += points;
	}

	function addPointsToYellow(points) {
		scoreTeamYellow += points;
	}
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<h1>Birthday Movie Scoring</h1>
<section>
	<div class="team red">
		<div class="buttons">
			<button on:click={addPointsToRed(100)}>
				+100
			</button>
			<button on:click={addPointsToRed(200)}>
				+200
			</button>
			<button on:click={addPointsToRed(500)}>
				+500
			</button>
		</div>
		<span>{scoreTeamRed}</span>
	</div>
	<div class="team yellow">
		<div class="buttons">
			<button on:click={addPointsToYellow(100)}>
				+100
			</button>
			<button on:click={addPointsToYellow(200)}>
				+200
			</button>
			<button on:click={addPointsToYellow(500)}>
				+500
			</button>
		</div>
		<span>{scoreTeamYellow}</span>
	</div>
</section>

<style>
	section {
		display: flex;
	}

	button {
		background-color: dark-purple;
		color: white;
		padding: 20px 50px;
		border-radius: 8px;
	}

	.buttons {
		display: flex;
		justify-content: space-evenly;
		height: 50px;
	}

	.team {
		padding: 20px 20px;
		width: 50%;
		height: 75vh;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.red {
		background-color: red;
	}

	.yellow {
		background-color: yellow;
	}

	h1 {
		width: 100%;
	}
</style>

