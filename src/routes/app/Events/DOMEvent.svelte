<script lang="ts">

	let showPointerPosition = $state(true)
	let m = $state({ x: 0, y: 0 })

	function onPointerMove(e: PointerEvent) {
		m.x = e.clientX
		m.y = e.clientY
	}

	function togglePointerPosition() {
		showPointerPosition = !showPointerPosition
	}

</script>

<button onclick={togglePointerPosition}>
	{showPointerPosition ? 'Hide Pointer Postion' : 'Show Pointer Position'}
</button>

<div onpointermove={onPointerMove} role="presentation">
	{#if showPointerPosition}
		The Pointer is at {Math.round(m.x)} x {Math.round(m.y)}
	{/if}
</div>

<style>
    div {
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