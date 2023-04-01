<script lang="ts">
  import ContactEntry from "$lib/widgets/home/ContactEntry.svelte";
  import InfoPanel from "$lib/widgets/home/InfoPanel.svelte";
</script>

<svelte:head>
  <title>szalovszky.me</title>
  <meta name="description" content="szalovszky.me" />
  <meta name="direction" content="-1" />
</svelte:head>

<div class="flex flex-col md:flex-row gap-8 justify-between">
  <div class="flex grow gap-5">
    <img width="72" src="$lib/images/wave.svg" alt="Wave" />
  </div>
  <div class="flex basis-4/5 flex-col sm:flex-row gap-8">
    <InfoPanel title="contact">
      <table>
        <ContactEntry
          key="email"
          value="david@szalovszky.com"
          link="mailto:david@szalovszky.com"
        />
        <ContactEntry
          key="github"
          value="szalovszky"
          link="https://github.com/szalovszky"
        />
        <ContactEntry
          key="discord"
          value="szalovszky#6309"
          link="https://discord.com/users/1014973658059522098"
        />
      </table>
    </InfoPanel>
  </div>
</div>

<style lang="scss">
  div:first-of-type {
    & > img {
      animation: 2s ease-in-out 0.5s alternate wave;
      transform-origin: 70% 70%;
    }
  }

  @keyframes wave {
    0% {
      transform: rotate(0);
    }

    10%,
    30%,
    50%,
    70% {
      transform: rotate(-7.5deg);
    }

    20%,
    40%,
    60% {
      transform: rotate(20deg);
    }

    80% {
      transform: rotate(10deg);
    }

    90% {
      transform: rotate(-3.75deg);
    }

    100% {
      transform: rotate(0);
    }
  }
</style>
