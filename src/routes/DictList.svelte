<script lang="ts">
	let dicts = ['JmDict', 'JnDict', 'SuperDict', 'スーパー辞書'].map((dict, i) => {
		return { dict, i, checked: true };
	});

	function move(up: boolean, old_index: number) {
		if ((!up && old_index + 1 == dicts.length) || (up && old_index == 0)) return;
		let new_index = old_index + (up ? -1 : 1);
		dicts.splice(new_index, 0, dicts.splice(old_index, 1)[0]);
		dicts = [...dicts];
	}
</script>

<div>
	{#each dicts as { dict, checked }, i}
		<article>
			<h3>{dict} <span>ver. 1.0.0</span></h3>
			<input type="checkbox" bind:checked />
			<div class="arrows">
				<button
					on:click={() => {
						move(true, i);
					}}>⏫</button
				>
				<button
					on:click={() => {
						move(false, i);
					}}>⏬</button
				>
			</div>
		</article>
	{/each}
</div>

<style lang="scss">
	article {
		display: flex;
		align-items: center;
		gap: 16px;
		&:not(:last-child) {
			border-bottom: 1px solid #cccccc;
		}
		h3 {
			font-size: 1rem;
			flex-grow: 1;
			span {
				font-weight: normal;
				opacity: 0.9;
			}
		}
	}
	input {
		width: 16px;
		height: 16px;
	}
	.arrows {
		display: flex;
		flex-direction: column;
	}
</style>
