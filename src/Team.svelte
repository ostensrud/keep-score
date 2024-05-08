<script lang="ts">
	export let teamName: string;
	let goals = 0;
	const addGoal = () => goals++;
	const subtractGoal = () => {
		if (goals > 0) {
			goals--;
		}
	};
</script>

<section class="section">
	<h2>{teamName}</h2>
	<div class="score">{goals}</div>
	<div class="buttons">
		<button on:click={subtractGoal}></button>
		<button on:click={addGoal}></button>
	</div>
</section>

<style>
	.buttons {
		display: grid;
		grid-template-columns: 1fr 5fr;

		min-height: 40vh;
	}

	.buttons > button {
		border: none;
		background: transparent;
	}

	.buttons > button + button {
		border-left: 2px solid #000;
	}

	.section {
		position: relative;
	}

	.score {
		position: absolute;
		top: 40%;
		left: 50%;

		font-size: 8rem;
		z-index: -1;
	}
</style>
