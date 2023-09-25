<script lang="ts">
	export let width: number;
	export let height: number;
</script>

<div>
	<div><span>width</span><input type="number" bind:value={width} /></div>
	<div><span>height</span><input type="number" bind:value={height} /></div>
</div>

<style lang="scss">
	div {
		display: flex;
		div {
			flex-direction: column;
			&:first-child {
				margin-right: 8px;
			}
		}
	}
	input {
		width: 80px;
	}
	span {
		font-size: 0.85rem;
	}
</style>
