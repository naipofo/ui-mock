<script lang="ts">
	export let selected: number = 0;
	export let values: string[];
</script>

<select bind:value={selected}>
	{#each values as value, i}
		<option value={i}>{value}</option>
	{/each}
</select>
