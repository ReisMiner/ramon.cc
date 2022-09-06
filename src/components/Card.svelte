<script>
    export let head;
    export let text;
    export let img;
</script>
<section>
    <div>
        <h1>{head}</h1>
        <img src="{img}" alt=""/>
    </div>
    <p>{text}</p>
</section>

<style>
    section {
        margin: 10px;
        height: 300px;
        width: 500px;
        max-width: 90vw;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.20);
        padding: 20px 10px 10px;
    }

    img {
        height: 100px;
        width: auto;
        right: 0;
    }

    h1 {
        margin:0;
        flex-grow: 20;
    }

    div {
        display: flex;
        flex-direction: row;
        align-content: flex-start;
        box-shadow: 0 5px 5px 0 rgba(0, 0, 0, 0.20);
    }
</style>