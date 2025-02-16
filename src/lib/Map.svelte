<script lang="ts">
	import { onMount, onDestroy } from 'svelte';
	import type { Map, LatLngExpression } from 'leaflet';
	import { browser } from '$app/environment';
	import heartIcon from '$lib/images/heart.png';
	import homeIcon from '$lib/images/home.png';

	interface Props {
		markers?: {
			name: string;
			link: string;
			coordinates: LatLngExpression;
			googleMapsID: string;
		}[];
	}

	let { markers = [] }: Props = $props();

	const COORDINATES_MUTIMBAUCH: LatLngExpression = [48.5836, 8.1472];

	let mapElement: HTMLElement;
	let map: Map;

	onMount(async () => {
		if (browser) {
			const leaflet = await import('leaflet');
			map = leaflet.map(mapElement, { scrollWheelZoom: false }).setView(COORDINATES_MUTIMBAUCH, 14);

			leaflet
				.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
					attribution:
						'&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
				})
				.addTo(map);

			markers.forEach((m) => {
				leaflet
					.marker(m.coordinates, {
						icon: leaflet.icon({
							iconUrl: homeIcon,
							iconSize: [30, 30]
						})
					})
					.addTo(map)
					.bindPopup(
						`<strong>${m.name}</strong><br /><br /><a href="${m.link}" target="_blank" rel="noopener noreferrer">Zur Website</a><br /><br /><a href="https://maps.app.goo.gl/${m.googleMapsID}" target="_blank" rel="noopener noreferrer">Zu Google Maps</a>`
					);
			});

			leaflet
				.marker(COORDINATES_MUTIMBAUCH, {
					icon: leaflet.icon({
						iconUrl: heartIcon,
						iconSize: [50, 50]
					})
				})
				.addTo(map)
				.bindPopup(
					'<strong>Lebenshof Mut im Bauch</strong><br /><br /><a href="https://lebenshof-mutimbauch.de/" target="_blank" rel="noopener noreferrer">Zur Website</a><br /><br /><a href="https://maps.app.goo.gl/rGpZ7awpXJhwmpQq7" target="_blank" rel="noopener noreferrer">Zu Google Maps</a>'
				);
		}
	});

	onDestroy(async () => {
		if (map) {
			map.remove();
		}
	});
</script>

<!-- Workaround for import bug in Leaflet CSS -->
<svelte:head>
	<link
		rel="stylesheet"
		href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
		integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY="
		crossorigin=""
	/>
</svelte:head>

<div class="h-full" bind:this={mapElement}></div>

<style>
</style>
