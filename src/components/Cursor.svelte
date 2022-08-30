<script>
    import jQuery from "jquery";
    //import {cursorVisible} from "./stores";

    let privVisible;
    // cursorVisible.subscribe(function (value){
    //     privVisible = value;
    // })

    let Cursor = null;

    jQuery(function () {
        Cursor = document.querySelector(".cursor");
    })

    document.addEventListener("mousemove", moveCursor)

    function moveCursor(e) {
        let x = e.pageX;
        let y = e.pageY;
        Cursor.style.left = x + 'px';
        Cursor.style.top = y + 'px';
        Cursor.style.left = x - 33 + 'px';
        Cursor.style.top = y - 39 + 'px';
    }

</script>
<div class="cursor" style="--visible: {privVisible}">
    <svg viewBox="-5 -5 110 110" fill="none">
        <polygon points="50 15, 100 100, 0 100"/>
    </svg>
</div>
<style>
    /*region Cursor*/
    .cursor {
        top: -100%;
        z-index: 100;
        width: 70px;
        height: 70px;
        position: absolute;
        pointer-events: none;
        opacity: var(--visible);
    }

    .cursor svg {
        stroke: white;
        stroke-width: 5px;
        transform-origin: 50% 66.66%;
        animation: triangle-rot 3s linear infinite;
    }

    @keyframes triangle-rot {
        0% {
            transform: rotate(0deg) scale(1, 1);
        }
        20% {
            transform: rotate(72deg) scale(0.8, 0.8);
        }
        40% {
            transform: rotate(144deg) scale(1, 1);
        }
        60% {
            transform: rotate(216deg) scale(0.7, 0.7);
        }
        80% {
            transform: rotate(288deg) scale(0.9, 0.9);
        }
        100% {
            transform: rotate(360deg) scale(1, 1);
        }
    }
</style>