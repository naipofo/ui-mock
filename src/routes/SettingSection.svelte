<script lang="ts">
	export let title: string;
</script>

<article>
	<header>
		{title}
	</header>
	<main>
		<slot />
	</main>
</article>

<style lang="scss">
	article {
		width: min(800px, calc(100vw - 40px));
	}
	main {
		background-color: white;
	}
	header {
		font-size: 1.4rem;
		padding-left: 1rem;
	}
</style>
