<script>
  import "fluent-svelte/theme.css";
  import { onMount } from 'svelte';
  import { Button, TextBlock } from 'fluent-svelte';
  import Buttons from './lib/Buttons.svelte';
  import { fade, slide, scale } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';

  const open = () => {
    alert('hi');
  }

  let ready = false;
  onMount(() => ready = true);
</script>
{#if ready}
<div in:fade="{{delay: 100, duration: 1000, easing: quintOut }}" class="gamgians">
  <TextBlock variant="display">
    hi
  </TextBlock>
</div>
<div in:fade="{{delay: 1000, duration: 1000, easing: quintOut }}" class="gamgians2">
  <TextBlock variant="subtitle">
    hello :pepeSmile:
  </TextBlock>
</div>
<div in:fade="{{delay: 2500, duration: 1000, easing: quintOut }}">
  <p> </p>
  <hr />
  <p> </p>
  <Buttons />
</div>
{/if}

<style>
  .gamgians {
    font-size: xx-large;
  }
  .gamgians2 {
    font-size: medium;
  }
</style>