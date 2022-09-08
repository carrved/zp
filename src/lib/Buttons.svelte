<script>
    import "fluent-svelte/theme.css";
    import { Button } from 'fluent-svelte';

    function downloadFile(url, fileName) {
        fetch(url, { method: 'get', mode: 'no-cors', referrerPolicy: 'no-referrer' })
            .then(res => res.blob())
            .then(res => {
            const aElement = document.createElement('a');
            aElement.setAttribute('download', fileName);
            const href = URL.createObjectURL(res);
            aElement.href = href;
            aElement.setAttribute('target', '_blank');
            aElement.click();
            URL.revokeObjectURL(href);
        });
    };

    const downloadTmClient = () => {
        console.log('trying to download tm client...');
        downloadFile("./lib/totalmath.html", "tm.html");
        console.log('downloaded')
    }
</script>

<Button variant="accent" on:click={downloadTmClient}>
    tm client
</Button>