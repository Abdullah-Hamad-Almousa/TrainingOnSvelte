<script lang="ts">

    import Counter from './app/counter.svelte'
    import DeepState from "./app/DeepState.svelte"
    import TestString from "./app/testString.svelte"
    import Effect from "./app/effect.svelte"
    import UniCounter from "./app/UniversalCounter.svelte"

</script>

<main>

    <section class="counter">

        <Counter />

    </section>

    <br>

    <section class="deep-state">

        <DeepState />

    </section>

    <br>

    <section class="test-string">

        <TestString ./>

    </section>

    <br>

    <section class="effect">

        <Effect />

    </section>

    <section class="uni-counter">

        <UniCounter /> <UniCounter /> <UniCounter />

    </section>

</main>

<style>

    :global(body){
        background: #882233;
    }

    .counter {
        background: aqua;
        padding: 30px;
    }

    .deep-state {
        background: #f8e32d;
        padding: 30px;
    }

    .test-string{
        background: gray;
        padding: 30px;
    }

    .effect{
        background: darkslategray;
        padding: 30px;
    }

</style>