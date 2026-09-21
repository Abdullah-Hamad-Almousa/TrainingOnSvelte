<script>

    import Counter from './counter.svelte'
    import DeepState from "./DeepState.svelte";
    import TestString from "./testString.svelte";
    import Effect from "./effect.svelte";

</script>

<main>

    <section class="counter">

        <Counter />

    </section>

    <br>

    <section class="deepState">

        <DeepState />

    </section>

    <br>

    <section class="testString">

        <TestString ./>

    </section>

    <br>

    <section class="effect">

        <Effect />

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

    .deepState {
        background: #f8e32d;
        padding: 30px;
    }

    .testString{
        background: gray;
        padding: 30px;
    }

    .effect{
        background: darkslategray;
        padding: 30px;
    }

</style>