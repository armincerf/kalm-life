<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import logo from '../../static/kalm.png';
	import logoWebp from '../../static/kalm.webp';
	import panikLogo from '../../static/extraPanik.png';
	import panikLogoWebp from '../../static/extraPanik.webp';

	let kalmImg = logo;
	let kalmWebp = logoWebp;
	const enterLogo = () => (kalmImg = panikLogo);
	const exitLogo = () => (kalmImg = logo);
	const enterLogop = () => (kalmWebp = panikLogoWebp);
	const exitLogop = () => (kalmWebp = logoWebp);
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<div class="welcome">
			<picture>
				<source
					srcset={kalmWebp}
					on:mouseleave={exitLogop}
					on:mouseenter={enterLogop}
					type="image/webp"
				/>
				<img src={kalmImg} on:mouseleave={exitLogop} on:mouseenter={enterLogop} alt="Welcome" />
			</picture>
		</div>

		Welcome to Kalm.Life
	</h1>

	<h2>
		This is a minimal template site for my app, Kalm Routines. <br /> More will be added here later,
		but for now see
		<a
			target="_blank"
			href="https://www.armincerf.com/2021/07/making-a-mobile-app-with-clojurescript-in-2021"
			>this blog post.</a
		>
	</h2>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		object-fit: contain;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
