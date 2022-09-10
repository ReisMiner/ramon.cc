<script>
    import {onMount} from 'svelte'
    import {fade} from 'svelte/transition'
    import {fly} from 'svelte/transition'
    import Cursor from "./components/Cursor.svelte";
    import Card from "./components/Card.svelte";
    import SocialLink from "./components/SocialLink.svelte";

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
            <h1 class="section-header">Skills / Projects (need to decide)</h1>
            <div class="cardContainer">
                <Card head="soon™" text="soon... or maybe I don't have any skillz :(" img="./pepe.png"></Card>
                <Card head="soon™" text="soon... or maybe I don't have any projects :(" img="./pepe.png"></Card>
                <Card head="soon™" text="soon... or maybe I don't have any skillz :(" img="./pepe.png"></Card>
                <Card head="soon™" text="soon... or maybe I don't have any projects :(" img="./pepe.png"></Card>
                <Card head="soon™" text="soon... or maybe I don't have any skillz :(" img="./pepe.png"></Card>
                <Card head="soon™" text="soon... or maybe I don't have any projects :(" img="./pepe.png"></Card>
            </div>
        </section>
        <section>
            <h1 class="section-header">Uh some links ig</h1>
            <div class="cardContainer">
                <SocialLink text="YouTube" lnk="https://youtube.com/ReisMiner"></SocialLink>
                <SocialLink text="Twitter" lnk="https://twitter.com/ReisMiner"></SocialLink>
                <SocialLink text="Github" lnk="https://github.com/ReisMiner"></SocialLink>
                <SocialLink text="Discord" lnk="https://discord.com/users/215136536260378624"></SocialLink>
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

    .section-header {
        margin-bottom: 5vh;
    }

    strong {
        color: coral;
        font-weight: bold;
    }

    header div {
        display: flex;
        flex-direction: column;
        width: max-content;
    }

    @media only screen and (max-width: 382px) {
        header div {
            text-align: center;
        }
    }

    header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 75vh;
        padding: 10px;
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
        flex-direction: column;
        align-items: center;
        padding: 100px;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.10);

    }

    .cardContainer {
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        justify-content: center;
    }

</style>