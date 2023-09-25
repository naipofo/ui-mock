<script lang="ts">
	export let check: boolean;
</script>

<input type="checkbox" bind:checked={check} />

<style lang="scss">
	input {
		width: 16px;
		height: 16px;
	}
</style>
