<script lang="ts">

	let countBlock = $state(0)

	function increment() {
		countBlock +=1
	}

</script>

<button onclick={increment}>
	Clicked {countBlock} times
</button>

{#if countBlock > 10} <!-- I did not like have count block down here but in the tutorial -->
	<p> <!-- { countBlock } --> is greater than 10 </p>
{:else if countBlock < 5}
	<p> <!-- { countBlock } --> is is less than 5</p>
{:else}
	<p> <!-- { countBlock } --> is between 5 and 10 </p>
{/if}