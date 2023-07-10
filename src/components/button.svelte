<script lang="ts">
	export let buttonText: String = "";
	export let callBack: Function = () => {};

	function handleClick() {
		callBack();
	}
</script>

<button on:click={handleClick}>{buttonText}</button>

<style>
</style>
