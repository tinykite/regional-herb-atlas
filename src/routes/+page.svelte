<script lang="ts">
	import type { PageData } from './$types';
	import Map from '../components/Map.svelte';
	interface Props {
		data: PageData;
	}

	let { data }: Props = $props();
	const { farms } = data;
</script>

<nav class="nav">
	<svg
		class="logo"
		aria-hidden="true"
		viewBox="0 0 28 28"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M14.0022 0C6.26552 0 0 6.26892 0 14C0 21.7311 6.26552 28 14.0022 28C21.7389 28 28 21.7311 28 14C28 6.26892 21.7345 0 14.0022 0ZM13.1834 23.8499L2.30305 12.9712C5.26724 12.1789 8.55543 12.945 10.8804 15.2695C13.2053 17.5941 13.9715 20.8862 13.1834 23.8499ZM14.0022 15.4578L13.5468 14.9106C12.4916 13.733 11.4408 12.5335 10.3856 11.3077C10.0441 10.9093 9.70258 10.5153 9.36982 10.1213C9.19031 9.91995 8.06943 8.60225 8.36278 6.83802C8.41532 6.51407 8.62987 5.192 9.78139 4.51345C10.9636 3.81739 12.4391 4.23327 13.2973 4.86804C13.6256 5.10882 13.8533 5.37148 14.0022 5.57286C14.1467 5.37148 14.3744 5.10882 14.7027 4.86804C15.5609 4.23327 17.0364 3.81739 18.2186 4.51345C19.3701 5.192 19.5847 6.51407 19.6372 6.83802C19.9306 8.60225 18.8097 9.91995 18.6302 10.1213C18.2974 10.5153 17.9559 10.9093 17.6144 11.3077C16.5636 12.5335 15.5084 13.733 14.4532 14.9106L14.0022 15.4578ZM14.8166 23.8499C14.0285 20.8862 14.7947 17.5941 17.1196 15.2695C19.4446 12.945 22.7328 12.1789 25.697 12.9712L14.8166 23.8499Z"
			fill="#231F20"
		/>
	</svg>
	<h1 class="nav__siteTitle">Herbalism Atlas</h1>
</nav>

<Map mapPoints={farms} />

<h2>By Name — {farms.length} Farms</h2>
<ul>
	{#each farms as farm}
		<li>{farm.Name}</li>
	{/each}
</ul>

<style>
	.nav {
		display: grid;
		grid-template-columns: 24px 1fr;
		align-items: center;
		gap: 0.5rem;
		position: absolute;
		left: 1rem;
		top: 1rem;
		width: 100vw;
		z-index: 200;
	}

	.nav__siteTitle {
		font-family: 'pressio-condensed', sans-serif;
		font-weight: 600;
		font-style: normal;
	}
</style>
