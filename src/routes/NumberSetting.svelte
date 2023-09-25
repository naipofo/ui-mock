<script lang="ts">
	export let number: number;
	export let min: number = 1;
	export let max: number = 100;
</script>

<input type="number" bind:value={number} {min} {max} />
