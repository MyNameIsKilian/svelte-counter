<script lang="ts">
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcomeFallback from '$lib/images/svelte-welcome.png';

	let scoreTeamRed = $state(0);
	let scoreTeamYellow = $state(0);

	function addPointsToRed(points) {
		scoreTeamRed += points;
	}

	function addPointsToYellow(points) {
		scoreTeamYellow += points;
	}

	function reset(color) {
		color == "red" ? scoreTeamRed = 0 : scoreTeamYellow = 0;
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
			<button onclick={() => addPointsToRed(100)}>
				+ 100
			</button>
			<button onclick={() => addPointsToRed(200)}>
				+ 200
			</button>
			<button onclick={() => addPointsToRed(500)}>
				+ 500
			</button>
			<button onclick={() => reset("red")}>
				Reset
			</button>
		</div>
		<span>{scoreTeamRed}</span>
	</div>
	<div class="team yellow">
		<div class="buttons">
			<button onclick={() => addPointsToYellow(100)}>
				+ 100
			</button>
			<button onclick={() => addPointsToYellow(200)}>
				+ 200
			</button>
			<button onclick={() => addPointsToYellow(500)}>
				+ 500
			</button>
			<button onclick={() => reset("yellow")}>
				Reset
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
		background-color: purple;
		color: white;
		padding: 0px 50px;
		border-radius: 8px;
		border: none;
		margin: 10px 30px;
		height: 50px;
	}

	span {
		font-size: 250px;
	}

	.buttons {
		display: flex;
		justify-content: space-evenly;
		height: 50px;
		margin-bottom: 80px;
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

