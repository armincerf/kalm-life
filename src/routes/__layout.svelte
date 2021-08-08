<script lang="ts">
	import Header from '$lib/header/Header.svelte';
	import '../app.css';
	import splitbee from '@splitbee/web';
	import { browser, dev } from '$app/env';

	const year = new Date().getFullYear();

	if (!dev && browser) {
		console.log('hello?', splitbee);
		
		splitbee.init({
			token: 'B9S7RRGFG7CU',
			scriptUrl: '/bee.js',
			apiUrl: '/_hive'
		});
	}
</script>

<Header />

<main>
	<slot />
</main>

<footer class="footer-distributed">
	<div class="footer-left">
		<p class="footer-links">
			<a class="link-1" href="/kalm-routines-privacy-policy">Kalm Routines Privacy Policy</a>
			<a class="link-1" href="/kalm-routines-terms">Kalm Routines Terms and Conditions</a>
		</p>

		<p>Alex Davis &copy; {year}</p>
	</div>
	<div class="footer-right">
		<a aria-label="Twitter" href="https://twitter.com/alexthings1"><i class="fab fa-twitter" /></a>
		<a aria-label="Github" href="https://github.com/armincerf"><i class="fab fa-github" /></a>
	</div>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	.footer-distributed {
		background-color: #292c2f;
		box-shadow: 0 1px 1px 0 rgba(0, 0, 0, 0.12);
		box-sizing: border-box;
		width: 100%;
		text-align: left;
		font: normal 16px sans-serif;
		padding: 45px 50px;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	.footer-distributed .footer-left p {
		color: #8f9296;
		font-size: 14px;
		margin: 0;
	}
	/* Footer links */

	.footer-distributed p.footer-links {
		font-size: 18px;
		font-weight: bold;
		color: #ffffff;
		margin: 0 0 10px;
		padding: 0;
		transition: ease 0.25s;
	}

	.footer-distributed p.footer-links a {
		display: block;
		line-height: 1.8;
		text-decoration: none;
		color: inherit;
		transition: ease 0.25s;
		padding-bottom: 10px;
	}

	.footer-distributed .footer-links a:before {
		content: '·';
		font-size: 20px;
		left: 0;
		color: #fff;
		display: inline-block;
		padding-right: 5px;
	}

	.footer-distributed .footer-links .link-1:before {
		content: none;
	}

	.footer-distributed .footer-right a {
		display: inline-block;
		width: 35px;
		height: 35px;
		background-color: #33383b;
		border-radius: 2px;
		font-size: 20px;
		color: #ffffff;
		text-align: center;
		line-height: 35px;
		margin-left: 3px;
		transition: all 0.25s;
	}

	.footer-distributed .footer-right a:hover {
		transform: scale(1.1);
		-webkit-transform: scale(1.1);
	}

	.footer-distributed p.footer-links a:hover {
		text-decoration: underline;
	}

	/* Media Queries */

	@media (max-width: 600px) {
		.footer-distributed {
			flex-direction: column;
		}
		.footer-distributed .footer-left,
		.footer-distributed .footer-right {
			text-align: center;
			padding-bottom: 1em;
		}

		.footer-distributed .footer-left p.footer-links {
			line-height: 1.8;
		}
	}
</style>
