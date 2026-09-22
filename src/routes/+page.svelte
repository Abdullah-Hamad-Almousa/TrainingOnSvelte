<script lang="ts">

    import Counter from './app/counter.svelte'
    import DeepState from "./app/DeepState.svelte"
    import TestString from "./app/testString.svelte"
    import Effect from "./app/effect.svelte"
    import UniCounter from "./app/UniversalCounter.svelte"
    import DeclaringProps from './app/DeclaringProps.svelte';
    import PackageInfo from './app/PackageInfo.svelte';

    const pkg = {
        name: 'svelte',
        version: 5,
        description: 'blazing fast',
        website: 'https://svelte.dev'
    }

</script>

<main>

    <section class="counter">

        <Counter />

    </section>

    <section class="deep-state">

        <DeepState />

    </section>

    <section class="test-string">

        <TestString ./>

    </section>

    <section class="effect">

        <Effect />

    </section>

    <section class="uni-counter">

        <UniCounter /> <UniCounter /> <UniCounter />

    </section>

    <section class="declaring-props">

        <div class="counter-row"><DeclaringProps answer={42} /> <DeclaringProps/></div>

    </section>

    <section class="package-info">

        <PackageInfo {...pkg}

        />

    </section>

</main>

<style>

    main {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    :global(body){
        background: #882233;
    }

    .counter {
        background: aqua;
        padding: 1px;
        padding-left: 30px
    }

    .deep-state {
        background: #f8e32d;
        padding: 1px;
        padding-left: 30px
    }

    .test-string{
        background: gray;
        padding: 1px;
        padding-left: 30px
    }

    .effect{
        background: darkslategray;
        padding: 1px;
        padding-left: 30px
    }

    .uni-counter{
        background: #76ba67;
        padding: 1px;
        padding-left: 30px
    }

    .declaring-props{
        background: #efeff1;
        padding: 1px;
        padding-left: 30px
    }

    .counter-row{
        display: flex;
        align-items: center;
        gap: 2rem;
    }

    .package-info{
        background: #9191f1;
        padding: 1px;
        padding-left: 30px
    }

</style>