<script>
    import "fluent-svelte/theme.css";
    import { Button } from 'fluent-svelte';

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
</script>

<Button variant="accent" on:click={tm}>
    t
</Button>

<Button variant="accent" on:click={v}>
    v
</Button>

<Button variant="accent" on:click={inv}>
    i
</Button>

<Button variant="accent" on:click={n}>
    n
</Button>