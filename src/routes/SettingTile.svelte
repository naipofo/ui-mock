<script lang="ts">
	export let title: String;
	export let desc: String;
</script>

<div>
	<header>
		<h1>{title}</h1>
		<span>{desc}</span>
	</header>

	<slot />
</div>

<style lang="scss">
	header {
		flex-grow: 1;
		* {
			font-size: 1rem;
		}
		h1 {
			margin: 0;
			font-weight: bold;
		}
		span {
			font-weight: normal;
			color: #222;
		}
	}

	div {
		width: 100%;
		display: flex;
		align-items: center;
		border-bottom: 1px solid #cccccc;
		padding: 1rem;
	}
</style>
