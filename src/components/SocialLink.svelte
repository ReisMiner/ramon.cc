<script>
    export let text;
    export let lnk;
</script>

<section>
    <a href="{lnk}">{text}</a>
</section>

<style>
    section {
        margin: 10px;
        width: 90px;
        height: 90px;
        box-shadow: 0 0 20px rgba(255, 127, 80, 0.20);
        display: grid;
        place-items: center;
        border-radius: 20px;
        transition: 0.2s;
        transition-timing-function: ease-in;
    }

    a{
        text-decoration: none;
        color: rgba(255, 255, 255, 0.87);
        cursor: none;
    }

    section:hover{
        box-shadow: 0 0 20px rgba(255, 127, 80, 0.80);
    }
</style>