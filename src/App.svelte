<script>
    import {onMount} from 'svelte'
    import {fade} from 'svelte/transition'
    import {fly} from 'svelte/transition'
    import Cursor from "./components/Cursor.svelte";

    let animate = false

    onMount(() => {
        animate = true
    })
</script>
{#if animate}
    <main transition:fade="{{duration:800}}">
        <div>
            <h1>Hoi</h1>
            <h1>I'm <strong>Ramon</strong></h1>
        </div>
        <h2 transition:fly="{{y:200}}">This site is still in development!</h2>
    </main>
{/if}
<Cursor/>
<style>
    h1 {
        margin: 0;
    }

    h2 {
        position: fixed;
        bottom: 30px;
        margin: 0 auto;
        text-align: center;
        width: 100vw;
    }

    strong {
        color: coral;
        font-weight: bold;
    }

    div {
        display: flex;
        flex-direction: column;
    }

    main {
        display: grid;
        place-items: center;
        width: 100vw;
        height: 100vh;
    }

</style>