<script lang="ts">
	let comicWavePth = "/src/assets/comicWaves.png";
</script>

<div class="my-container relative h-screen w-screen italic sm:h-3/4">
	<!-- <div class="blur-sm h-full w-screen bg-[url('{comicWavePth}')]" /> -->
	<!-- top-1/2 w-1/3 -->
	<div class="textShadow absolute left-20 top-5 sm:top-1/2">
		<p class=" text-center text-9xl">WHY?</p>
	</div>
	<!-- top-1/2 left-1/2 w-1/3 -->
	<div
		class="glass textShadow top-1/3 before:mx-1 before:rounded-md before:absolute before:bottom-0 before:top-0 before:left-0 before:right-0 absolute sm:top-1/3 sm:w-1/3 sm:left-2/4"
	>
		<p class="text-4xl p-1 not-italic text-center">
			This website serves as an interaction tool to a server that
			implements worker pool concept. Users upload images to MongoDB
			via a Go-based gin-gonic server, and the server efficiently
			processes them. All data is purged after 15 minutes since its
			inserted into the database
		</p>
	</div>
</div>

<style>
	.glass::before {
		box-shadow: inset 0 0 20px rgba(0, 0, 0, 0.75);
	}
	.my-container::before {
		content: "";
		position: absolute;
		margin: 0%;
		padding: 0%;
		top: 0;
		left: -10%;
		right: -10%;
		bottom: 0;
		background-image: url("/src/assets/comicWaves.png");
		border-radius: 0.3em;
		filter: blur(5px);
	}
	.textShadow {
		text-shadow: 0 0 15px black;
	}
	/* .left,
		.right {
			width: 100%;
			height: 50%;
		}
		.left {
			padding-top: 50%;
		}
		.right > p {
			font-size: 0.85em;
		} */
</style>
