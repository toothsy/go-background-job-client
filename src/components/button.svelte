<script lang="ts">
	export let buttonText: String = "";
	export let callBack: Function = () => {};

	function handleClick() {
		console.log("HEY I FIRED THE CALLBACK");

		callBack();
	}
</script>

<button
	on:click={handleClick}
	class="bg-white text-4xl text-[#3F94BB] fixed top-4 right-4 z-10 rounded-3xl italic p-2 sm:right-8"
	>{buttonText}
</button>

<style>
	button {
		box-shadow: 6px 6px 0px 0px rgb(62, 148, 187);
	}
</style>
