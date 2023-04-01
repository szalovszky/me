<script lang="ts">
  import { onMount } from "svelte";
  import { fly } from "svelte/transition";

  export let path = "";

  const duration = 250;
  const amount = 20;

  let animations = false;

  onMount(
    () =>
      (animations = !window.matchMedia(`(prefers-reduced-motion: reduce)`)
        .matches)
  );
</script>

{#key path}
  {#if !!animations}
    <div
      in:fly={{
        x:
          amount *
          Number.parseInt(
            document.head
              .querySelector('meta[name="direction"]:last-of-type')
              ?.getAttribute("content") || "1"
          ),
        duration: duration,
        delay: duration,
      }}
      out:fly={{
        x:
          amount *
          -Number.parseInt(
            document.head
              .querySelector('meta[name="direction"]:last-of-type')
              ?.getAttribute("content") || "1"
          ),
        duration: duration,
      }}
    >
      <slot />
    </div>
  {:else}
    <slot />
  {/if}
{/key}
