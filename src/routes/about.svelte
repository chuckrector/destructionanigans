<script>
  import { onMount, onDestroy } from "svelte";
  import { fade } from "svelte/transition";
  import { zazu } from "../stores.js";

  onMount(() => {
    console.log("about: onMount");
  });

  onDestroy(() => {
    console.log("about: onDestroy");
  });
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

{#if $zazu}
  <h1 transition:fade>About this site</h1>

  <p>This is the 'about' page. There's not much here.</p>
{/if}
