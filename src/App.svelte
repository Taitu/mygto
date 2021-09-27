<script lang="ts">
	export let name: string;
	import cards from './constants/cards';
</script>

<main>
	<h1>Hello {name}!</h1>
	<div class="deck">
		<div class="deck-row">
			{#each cards as card}
				<div class="deck-row-item">
					{#each cards as second}
						{#if card.priority > second.priority}
							<div class="deck-row-item-box">
								<div>{card.name}</div>
								<div>{second.name}</div>
							</div>
						{:else}
							<div class="deck-row-item-box">
								<div>{second.name}</div>
								<div>{card.name}</div>
							</div>
						{/if}
					{/each}
				</div>
			{/each}
		</div>
	</div>
</main>

<style>
	.deck {
		display: flex;
	}
	.deck-row {
		/* display: flex; */
		border: 1px solid #ccc;
	}
	.deck-row-item {
		display: flex;
		border-bottom: 1px solid #ccc;
	}
	.deck-row-item:last-child {
		border-bottom: none;
	}
	.deck-row-item-box {
		padding: 5px;
		width: 30px;
		height: 30px;
		border-right: 1px solid #ccc;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.deck-row-item-box:last-child {
		border-right: none;
	}
</style>