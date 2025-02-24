<script lang="ts">
	import hero from '$lib/images/hero.jpg';
	import Schedule from './Schedule.svelte';
	import Venue from './Venue.svelte';
	import RSVP from './RSVP.svelte';
	import FAQ from './FAQ.svelte';
</script>

<img src={hero} alt="Ela, Lena und Rika" class="mb-20" />

<div class="mx-auto max-w-4xl">
	<div class="mb-24 text-center">
		<h1 class="mb-4 text-5xl md:text-8xl">Raphaela & Lena</h1>
		<p class="text-3xl md:text-6xl">20.09.2025</p>
	</div>

	<div class="mb-24 p-6 text-center text-3xl md:text-5xl">
		<p class="mb-8">
			Du hast uns auf unserem Weg begleitet und bist uns wichtig. Wir laden Dich herzlich dazu ein,
			unsere Liebe mit uns zu feiern.
		</p>
		<p class="mb-8">Am 20.9. 2025 heiraten wir auf dem Lebenshof "Mut im Bauch" im Schwarzwald.</p>
		<p>
			Erscheine so, wie Du Dich wohlfühlst. Sei einfach Du selbst, mit all Deinen Farben und dem,
			was Dich ausmacht.
		</p>
	</div>

	<Schedule />

	<Venue />

	<RSVP />

	<FAQ />
</div>
