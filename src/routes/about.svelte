<script context="module">
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<div class="content">
	<h1>About Kalm</h1>
	Kalm is an unfinished suite of tools designed to help you lead a more relaxed life.
	<br />
	See <a target="_blank" href="https://www.craft.do/s/nkh8fMw5AE095W">here</a> for a list of upcoming features.
	<h2>Kalm Routines</h2>
	<p>
		Kalm Routines is an iOS and android app that helps you stick to a list of tasks. You can define
		complex routines with multiple concurrent timed events and receive notifications to help keep
		you on track.
	</p>
</div>

<style>
	h2 {
		font-weight: 800;
		font-size: large;
	}
	.content {
		width: 100%;
		max-width: var(--column-width);
		margin: var(--column-margin-top) auto 0 auto;
	}
</style>
