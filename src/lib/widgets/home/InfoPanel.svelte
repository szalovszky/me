<script lang="ts">
  export let title: string;
</script>

<div class="grow">
  <p class="text-2xl font-bold mb-2">{title}</p>
  <slot />
</div>
