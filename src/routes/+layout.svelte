<script lang="ts">
  import type { LayoutData } from "./$types";
  import Transition from "$lib/components/Transition.svelte";
  import Footer from "$lib/widgets/Footer.svelte";

  import "../app.css";

  export let data: LayoutData;
</script>

<div class="h-full flex flex-col justify-between">
  <Transition path={data.pathname}>
    <main>
      <slot />
    </main>
  </Transition>
  <Footer />
</div>

<style lang="scss">
  @import "../lib/Colors.scss";
  @import "@fontsource/noto-sans";

  :root {
    $font: "Noto Sans", sans-serif;
    font-family: $font;
    color: $color-text;
  }

  :global(body) {
    background: $color-0;
  }
</style>
