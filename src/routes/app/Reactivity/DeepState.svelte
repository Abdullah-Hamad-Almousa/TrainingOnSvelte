<script lang="ts">

    let numbers = $state([1, 2, 3, 4]); //Deep State
    let total = $derived(numbers.reduce((t, n) => t + n, 0)); //Derived state

    function addNumber() {
        numbers.push(numbers.length + 1)
    }

    $inspect(numbers).with(console.trace) //Inspecting state

</script>

<p>{numbers.join(' + ')} = {total}</p>

<button onclick={addNumber}>
    Add a number
</button>