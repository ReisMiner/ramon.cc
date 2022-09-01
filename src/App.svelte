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

    function easterEgg() {
        count++;
        if (count >= 5) {
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
            <div class="cardContainer">
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
                <Card head="soon™" text="soon soon soon" img="./pepe.png"></Card>
            </div>
        </section>
    </main>
{/if}
<Cursor/>
<style>
    h1 {
        margin: 0;
        font-size: 3.2rem;
        line-height: 1.1;
    }

    strong {
        color: coral;
        font-weight: bold;
    }

    header div {
        display: flex;
        flex-direction: column;
    }

    header {
        display: grid;
        place-items: center;
        height: 75vh;
        background-color: #222;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.20);

    }

    main {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    section {
        display: flex;
        justify-content: center;
        padding: 100px;
    }

    .cardContainer {
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: center;
    }

</style>