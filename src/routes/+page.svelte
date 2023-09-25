<script lang="ts">
	import DimensionsSetting from './DimensionsSetting.svelte';
	import EnumSettings from './EnumSettings.svelte';
	import NumberSetting from './NumberSetting.svelte';
	import SettingTile from './SettingTile.svelte';
	import ToggleSetting from './ToggleSetting.svelte';

	let check: boolean;
	let number: number = 1;
	let width: number = 1;
	let height: number = 1;

	let values = ['None', 'Shift', 'Ctrl', 'Alt'];
	let selected: number = 1;
</script>

<div>
	<SettingTile title="Use AnkiConnect" desc="Use AnkiConnect api to create flashcards in Anki.">
		<ToggleSetting {check} />
	</SettingTile>

	<SettingTile
		title="Text scan length"
		desc="Change how many characters are read when scanning for terms"
	>
		<NumberSetting {number} />
	</SettingTile>

	<SettingTile title="Popup size" desc="Control the size of the popup, in pixels">
		<DimensionsSetting {width} {height} />
	</SettingTile>

	<SettingTile title="Scan modifier key" desc="Hold a key while moving the cursor to scan text">
		<EnumSettings {values} {selected} />
	</SettingTile>
</div>

<style lang="scss">
	div {
		width: min(600px, calc(100vw - 40px));
	}
	:global(body) {
		display: flex;
		flex-direction: column;
		align-items: center;

		font-family: Arial, sans-serif;
	}
</style>
