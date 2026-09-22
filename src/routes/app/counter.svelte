<script lang="ts">

    let count = $state(0); //State

    function increment() {
        count += 1;
    }

</script>

<button onclick={increment}>

    Clicked {count} times

</button>