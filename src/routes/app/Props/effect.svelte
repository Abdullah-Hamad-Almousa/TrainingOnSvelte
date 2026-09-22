<script lang="ts">

    let elapsed = $state(0)
    let interval = $state(1000)

    $effect(() => { //Effect
        const id = setInterval(() => {
            elapsed += 1
        }, interval)

        return () => {
            clearInterval(id)
        }
    })

</script>

<button onclick={() => interval /= 2}>Speed up</button>
<button onclick={() => interval *= 2}>Slow down</button>

<p>Elapsed: {elapsed}</p>