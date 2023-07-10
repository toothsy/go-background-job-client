<script lang="ts">
	import { onMount } from "svelte";
	import WhyPage from "./whyPage.svelte";

	const fw: string = "/src/assets/front-wave-3.PNG";
	const mw: string = "/src/assets/middle-wave-2.PNG";
	const mountain: string = "/src/assets/mountain.PNG";
	$: scrollYPosition = 0;
	$: leftHeaderXPosition = 0;
	let orignalX = 0;
	let divideFactor = 9;
	let leftHeader: HTMLElement;
	let rightHeader: HTMLElement;
	onMount(async () => {
		leftHeader = document.querySelector(".left");
		rightHeader = document.querySelector(".right");
		orignalX = leftHeader.getBoundingClientRect().x / divideFactor;
	});

	let scrollingDown: boolean = false;
	function updateScroll(e: Event) {
		if (
			scrollYPosition <
			document.querySelector(".content-wrapper").scrollTop
		) {
			scrollingDown = true;
		} else {
			scrollingDown = false;
			leftHeaderXPosition =
				leftHeader.getBoundingClientRect().x / divideFactor;
		}
		scrollYPosition =
			document.querySelector(".content-wrapper").scrollTop;
		if (scrollingDown && leftHeader) {
			leftHeader.style.transform = `translateX(-${
				scrollYPosition / divideFactor
			}px)`;
			rightHeader.style.transform = `translateX(${
				scrollYPosition / divideFactor
			}px)`;
		} else if (
			!scrollingDown &&
			leftHeader &&
			leftHeaderXPosition < orignalX
		) {
			leftHeader.style.transform = `translateX(${
				leftHeaderXPosition - scrollYPosition / divideFactor
			}px)`;
			rightHeader.style.transform = `translateX(${
				leftHeaderXPosition * -1 + scrollYPosition / divideFactor
			}px)`;
		}
	}
</script>

<div class="content-wrapper" on:scroll={updateScroll}>
	<header>
		<div class="header-wrapper">
			<h1 class="left">PHOTO</h1>
			<h1 class="right">GALLERY</h1>
		</div>
		<img src={fw} class="front-wave" alt="front-wave" />
		<img src={mw} class="middle-wave" alt="middle-wave" />
		<img src={mountain} class="mountain" alt="mountain" />
	</header>
	<WhyPage />
</div>

<style>
	.left,
	.right {
		margin: auto 8px;
	}

	.header-wrapper {
		display: flex;
		font-weight: 800;
		flex-direction: row;
		margin: auto;
		position: absolute;
		font-size: 4rem;
		color: hsl(162, 83%, 98%);
		text-shadow: 0 0 5px black;
		font-style: italic;
		transition: transform 0.3s ease;
	}
	.mountain,
	.middle-wave,
	.front-wave {
		object-fit: cover;
		position: absolute;
		height: 100%;
		width: 100%;
		z-index: -1;
	}
	.front-wave {
		transform: translateZ(-5px) scale(1.5);
		z-index: 0;
		top: -8%;
	}
	.middle-wave {
		transform: translateZ(-10px) scale(1.7);
		top: -5%;
	}
	.mountain {
		transform: translateZ(-14px) scale(2);
		top: -6%;
	}
	.content-wrapper {
		height: 100svh;
		overflow-y: auto;
		overflow-x: hidden;
		perspective: 15px;
	}

	header {
		position: relative;
		display: flex;
		top: 0;
		left: 0;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100%;
		transform-style: preserve-3d;
		z-index: -1;
	}
</style>
