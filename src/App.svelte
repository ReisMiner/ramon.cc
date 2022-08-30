<script>
    import {onMount} from 'svelte'
    import {fade} from 'svelte/transition'
    import {fly} from 'svelte/transition'
    import Cursor from "./components/Cursor.svelte";
    import Card from "./components/Card.svelte";

    let animate = false

    onMount(() => {
        animate = true
    })

    let count = 0;

    function easterEgg(){
        count ++;
        if(count >= 5){
            window.location.href = "./vid.mp4";
        }
    }

</script>
{#if animate}
    <main>
        <header transition:fade="{{duration:800}}">
            <div>
                <h1 on:click={easterEgg}>Hoi</h1>
                <h1>I'm <strong>Ramon</strong></h1>
                <h2 transition:fly="{{y:-200}}">This site is still in development!</h2>
            </div>
        </header>
        <section>
        </section>
    </main>
{/if}
<Cursor/>
<style>
    h1 {
        margin: 0;
    }

    strong {
        color: coral;
        font-weight: bold;
    }

    div {
        display: flex;
        flex-direction: column;
    }

    header,section {
        display: grid;
        place-items: center;
        max-height: 600px;
    }

    main {
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

</style>