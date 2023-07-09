<script lang="ts">
	import "overlayscrollbars/overlayscrollbars.css";
	import { OverlayScrollbarsComponent } from "overlayscrollbars-svelte";
	const fw = "/src/assets/front-wave-3.PNG";
	const mw = "/src/assets/middle-wave-2.PNG";
	const mountain = "/src/assets/mountain.PNG";
</script>

<OverlayScrollbarsComponent>
	<div class="content-wrapper">
		<header>
			<div class="header-wrapper">
				<h1 class="left">PHOTO</h1>
				<h1 class="right">GALLERY</h1>
			</div>
			<img src={fw} class="front-wave" alt="front-wave" />
			<img src={mw} class="middle-wave" alt="middle-wave" />
			<img src={mountain} class="mountain" alt="mountain" />
		</header>
		<section>
			Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum
			repudiandae quas quasi error dolorem praesentium non ex ea quia
			voluptates corrupti saepe officia ab dolores quod placeat,
			ratione corporis iste atque. Tempore tempora nihil omnis
			nesciunt, architecto doloremque officiis saepe ab autem
			obcaecati. Molestiae, magni et fugiat harum rerum vitae at quas
			aperiam modi quam quo quisquam cum veniam earum numquam corrupti
			cumque odit dolore, eligendi sed delectus. Numquam at hic ad
			explicabo iusto modi nisi inventore quidem quos minima ipsam
			quibusdam, temporibus veniam esse reiciendis ipsa incidunt et non
			nesciunt assumenda facere, ducimus iure sapiente quaerat!
			Repellat quisquam debitis totam, obcaecati incidunt placeat
			voluptatem temporibus nam porro delectus rem. Vero quis quibusdam
			esse consequuntur voluptate explicabo quisquam optio fugiat,
			culpa voluptatem aut suscipit molestiae ipsum beatae provident
			similique? Aspernatur possimus sed expedita, facilis ipsam labore
			quibusdam nobis repellat excepturi reprehenderit sunt placeat
			quia ab nostrum recusandae odit dolorum exercitationem corporis,
			nisi impedit. In fugiat eveniet molestias labore. Est
			repudiandae, quidem deserunt perspiciatis ex aut consequatur,
			minus tempore minima repellat nobis soluta natus expedita facilis
			rerum ab hic id voluptates! Est molestias explicabo, excepturi
			perferendis commodi non! Recusandae nam harum quasi praesentium
			facilis reiciendis, a quis enim reprehenderit laboriosam sed id
			nobis numquam odio culpa maiores mollitia ullam unde nisi
			similique fugit dolores blanditiis ex inventore. Magni autem
			cupiditate, laborum natus recusandae minima quo fugit facilis eos
			fuga voluptas rerum tenetur eveniet iusto commodi provident!
			Autem maxime aliquid quam? Vitae, earum!
		</section>
	</div>
</OverlayScrollbarsComponent>

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
		color: white;
		text-shadow: 0 0 5px black;
		font-style: italic;
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
