<script lang="ts">
	export let shown: boolean = false;
	export let title: string;

	let dialog: HTMLDialogElement;
	$: {
		if (shown && dialog) {
			dialog.showModal();
			dialog.addEventListener(
				'close',
				() => {
					shown = false;
				},
				{ once: true }
			);
		}
	}
</script>

<dialog bind:this={dialog}>
	<header>
		<h2>{title}</h2>
		<button on:click={(_) => dialog.close()}>X</button>
	</header>
	<main>
		<slot />
	</main>
</dialog>

<style lang="scss">
	dialog {
		width: min(600px, calc(100vw - 100px));
		height: min(400px, calc(100vh - 60px));
		border: 1px solid #ccc;

		padding: 16px;
	}
	header {
		display: flex;
		align-items: flex-start;
		margin-bottom: 16px;
		h2 {
			font-size: 1rem;
			flex-grow: 1;
			margin: 0;
		}
	}
</style>
