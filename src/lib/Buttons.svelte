<script>
    import "fluent-svelte/theme.css";
    import { Button } from 'fluent-svelte';
    import { fade, slide } from 'svelte/transition';
    import { quintOut } from 'svelte/easing';
    import { onMount } from "svelte";

    function iframe(urlin) {
        let win = window.open();
        let url = urlin;
        var frame = win.document.createElement('iframe');
        frame.style.width = '100%';
        frame.style.height = '100%';
        frame.style.border = 'none';
        frame.src = url;
        win.document.body.appendChild(frame);
    }

    const tm = () => {
        iframe("https://tranquil-naiad-f698d2.netlify.app/totalmath.html");
    }

    const v = () => {
        iframe("https://tranquil-naiad-f698d2.netlify.app/void/void.html")
    }

    const inv = () => {
        iframe("https://tranquil-naiad-f698d2.netlify.app/invidious/invidious.html")
    }

    const n = () => {
        iframe("https://tranquil-naiad-f698d2.netlify.app/nightmare/nightmare.html")
    }

    const e = () => {
        iframe("https://extrememath.net/");
    }

    let ready = false;
    onMount(() => ready = true);
</script>
{#if ready}
<div in:fade="{{delay: 100, duration: 1000, easing: quintOut }}" class="buttons">
    <Button on:click={tm}>
        t
    </Button>

    <Button on:click={v}>
        v
    </Button>

    <Button on:click={inv}>
        i
    </Button>

    <Button on:click={n}>
        n
    </Button>
    <Button on:click={e}>
        e
    </Button>
</div>
{/if}