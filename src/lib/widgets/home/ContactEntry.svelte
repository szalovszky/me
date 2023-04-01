<script lang="ts">
  export let key: string;
  export let link: string;
  export let value: string;
</script>

<tr>
  <td class="text-gray-400">{key}</td>
  <td class="pl-2"><a class="underline" href={link}>{value}</a></td>
</tr>
