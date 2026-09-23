<script lang="ts">

    import Counter from './app/Reactivity/counter.svelte'
    import DeepState from "./app/Reactivity/DeepState.svelte"
    import TestString from "./app/Reactivity/testString.svelte"
    import Effect from "./app/Props/effect.svelte"
    import UniCounter from "./app/Reactivity/UniversalCounter.svelte"
    import DeclaringProps from './app/Props/DeclaringProps.svelte';
    import PackageInfo from './app/Props/PackageInfo.svelte';
    import IfBlock from './app/Logic/ifBlock.svelte'
    import EachLogic from './app/Logic/eachLogic.svelte'
    import KeyEachBlock from './app/Logic/keyEachBlock.svelte'
    import Await from './app/Logic/await.svelte'
    import DOMEvent from './app/Events/DOMEvent.svelte';
    import Capturing from './app/Events/Capturing.svelte';
    import ComponentEvents from './app/Events/ComponentEvents.svelte';
    import SpreadingEvents from './app/Events/SpreadingEvents.svelte';

    const pkg = {
        name: 'svelte',
        version: 5,
        description: 'blazing fast',
        website: 'https://svelte.dev'
    }

    let value = $state(0)

    let things = $state([
        { id: 1, nameKey: 'Apple'},
        { id: 2, nameKey: 'Banana'},
        { id: 3, nameKey: 'Carrot'},
        { id: 4, nameKey: 'Doughnut'},
        { id: 5, nameKey: 'Egg'},
    ])

</script>

<main>

    <section class="domEvent">

        <Counter />

    </section>

    <section class="await">

        <DeepState />

    </section>

    <section class="domEvent">

        <TestString ./>

    </section>

    <section class="await">

        <Effect />

    </section>

    <section class="domEvent">

        <UniCounter /> <UniCounter /> <UniCounter />

    </section>

    <section class="await">

        <div class="counter-row"><DeclaringProps answer={42} /> <DeclaringProps/></div>

    </section>

    <section class="domEvent">

        <PackageInfo {...pkg}

        />

    </section>

    <section class="await">
        <IfBlock />
    </section>

    <section>

        <EachLogic />

    </section>

    <section class="domEvent counter-row">

        <button onclick={() => things.shift()}>
            Remove first thing
        </button>

        {#each things as thing (thing.id)}
            <KeyEachBlock nameKey={thing.nameKey} />
        {/each}

    </section>

    <section class="await">
        <Await />
    </section>

    <section class="domEvent">
        <DOMEvent />
    </section>

    <section class="await">
        <Capturing />
    </section>

    <section class="domEvent">
        <ComponentEvents
          increment={() => value += 1}
          decrement={() => value -= 1}
        />
        <p>The current value is {value}</p>
    </section>

    <section class="await">
        <SpreadingEvents />
    </section>

</main>

<style>

    .domEvent {
        background: #4c2f4f;
        padding: 1px;
        padding-left: 30px
    }

    .await {
        background: darkslategray;
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

    .counter-row{
        display: flex;
        align-items: center;
        gap: 2rem;
    }

</style>