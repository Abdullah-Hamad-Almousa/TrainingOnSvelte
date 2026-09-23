<script lang="ts">
	let showPointerPosition = $state(true);
	let m = $state({ x: 0, y: 0 });

	function onPointerMove(e: PointerEvent) {
		m.x = e.clientX;
		m.y = e.clientY;
	}

	function togglePointerPosition() {
		showPointerPosition = !showPointerPosition;
	}
</script>

<svelte:window onpointermove={onPointerMove} />

<button onclick={togglePointerPosition}>
	{showPointerPosition ? 'Hide Pointer Position' : 'Show Pointer Position'}
</button>

{#if showPointerPosition}
	<div class="pointer-area" onpointermove={onPointerMove} role="presentation">

		The Pointer is at {Math.round(m.x)} x {Math.round(m.y)}

	</div>
{/if}
<style>
    .pointer-area {
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        padding: 1rem;
				pointer-events: none;
    }

    button {
        position: relative;
        z-index: 1;
    }
</style>