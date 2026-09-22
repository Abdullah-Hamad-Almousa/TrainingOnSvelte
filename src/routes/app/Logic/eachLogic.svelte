<script lang="ts">

	const colors = ['orange', '#992233', '#ffdb49', '#228833', '#33228B', '#583845', '#293912'];
	let selected = $state(colors[0]);

</script>

<main class="color-picker" style="background-color: {selected}">

	<h1>Pick a colour</h1>

	<div >
		{#each colors as color, i (color)}
			<button
				style="background: {color}"
				aria-label={color}
				aria-current={selected === color}
				onclick={() => selected = color}
			>{i + 1}</button>
		{/each}
	</div>

</main>

<style>
    h1 {
        transition: color 0.2s;
        font-weight: 700;
    }

		.color-picker {
				padding: 0.5rem;
				transition: background-color 0.2s;
		}

    div {
        display: grid;
        grid-template-columns: repeat(7, 1fr);
        grid-gap: 5px;
        max-width: 50px;
    }

    button {
        aspect-ratio: 1;
        border-radius: 50%;
        background: var(--color, #f5f5f7);
        transform: translate(-2px,-2px);
        filter: drop-shadow(2px 2px 3px rgba(0,0,0,0.2));
        transition: all 0.1s;
        color: black;
        font-weight: 700;
        font-size: 2rem;
    }

    button[aria-current="true"] {
        transform: none;
        filter: none;
        box-shadow: inset 3px 3px 4px rgba(0,0,0,0.2);
    }
</style>