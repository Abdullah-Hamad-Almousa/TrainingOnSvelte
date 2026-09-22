<script lang="ts">

	import { counterSvelte } from "./scripts/counter.svelte.ts"

</script>

<button onclick={() => counterSvelte.count += 1}>
	clicks: {counterSvelte.count}
</button>