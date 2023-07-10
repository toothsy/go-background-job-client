<script lang="ts">
	import Button from "./components/button.svelte";
	import LandingPage from "./components/landingPage.svelte";

	let buttonText: string = "Upload";
</script>

<main>
	<Button {buttonText} />
	<LandingPage />
</main>

<style>
	main {
		overflow: hidden;
	}
</style>
