<script lang="ts">

    import Counter from './app/Reactivity/counter.svelte'
    import DeepState from "./app/Reactivity/DeepState.svelte"
    import TestString from "./app/Reactivity/testString.svelte"
    import Effect from "./app/Props/effect.svelte"
    import UniCounter from "./app/Reactivity/UniversalCounter.svelte"
    import DeclaringProps from './app/Props/DeclaringProps.svelte';
    import PackageInfo from './app/Props/PackageInfo.svelte';
    import IfBlock from './app/Logic/ifBlock.svelte'

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

    <section class="if-block">
        <IfBlock />
    </section>

</main>

<style>

    .if-block {
        background: #dd3737;
        padding: 1px;
        padding-left: 30px
    }

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