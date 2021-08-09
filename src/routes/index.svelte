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
	const enterLogo = () => {
		kalmWebp = panikLogoWebp;
		kalmImg = panikLogo;
	};
	const exitLogo = () => {
		kalmImg = logo;
		kalmWebp = logoWebp;
	};
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		<div class="welcome">
			<picture>
				<source srcset={kalmWebp} type="image/webp" />
				<img src={kalmImg} on:mouseleave={exitLogo} on:mouseenter={enterLogo} alt="Welcome" />
			</picture>
		</div>

		Hi.
	</h1>

	<h2>
		This is a minimal template site for my app, Kalm Routines. <br /> More will be added here later,
		but for now see
		<a
			target="_blank"
			rel="noopener"
			href="https://www.armincerf.com/2021/07/making-a-mobile-app-with-clojurescript-in-2021"
			>this blog post
		</a>
		<br/>or checkout the Kalm Routines app on the app stores:
		<div class="badges">
			<a href="https://itunes.apple.com/app/kalm-routines/id1578270343"
				><img class="app-store-badge" src="/app-store-badge.png" alt="Download on the app store" />
			</a>
			<a href="https://play.google.com/store/apps/details?id=com.armincerf.kalm_routines"
				><img
					class="google-play-badge"
					src="/play-store-badge.png"
					alt="Download on the play store"
				/>
			</a>
		</div>
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

	.badges {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		margin-top: 20px;
		cursor: pointer;
	}

	.badges img {
		max-height: 50px;
		margin: 10px;
		border-radius: 5px;
		transition: box-shadow 200ms;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
	}

	@media (max-width: 414px) {
		.badges img {
			max-height: 40px;
		}
	}

	.badges img:hover {
		box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
	}

	.badges img:active {
		transform: scale(0.98);
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
