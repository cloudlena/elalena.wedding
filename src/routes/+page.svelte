<script lang="ts">
	import heroine from './heroine.jpg';
</script>

<img src={heroine} alt="Ela, Lena und Rika" class="mb-20" />

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
		<p class="mb-8">Am 20.9. 2025 heiraten wir auf dem Lebenshof "MutimBauch" im Schwarzwald.</p>
		<p>
			Erscheine so wie Du Dich wohlfühlst. Sei einfach Du selbst, mit all Deinen Farben und dem was
			Dich ausmacht.
		</p>
	</div>

	<div class="mb-24 p-6 text-center text-3xl md:text-5xl">
		<h2 class="mb-4 text-4xl md:text-7xl">Programm</h2>
		<div class="flex w-full flex-col">
			<div class="flex flex-row gap-24">
				<div>ab 10:00</div>
				<div>Ankunft</div>
				<!-- Taxiservice? -->
			</div>
			<div class="flex flex-row gap-24">
				<div>11:00</div>
				<div>Brunch & Flammkuchen</div>
				<!-- Roggen Sauerteig, Züpfe und Croissants. süss und herzhaft stickers "Recommended by Ela/Lena" -->
			</div>
			<div class="flex flex-row gap-24">
				<div>13:30</div>
				<div>Kleiner Spaziergang (ca. 30 min)</div>
				<!-- 30min-45min -->
			</div>
			<div class="flex flex-row gap-24">
				<div>15:00</div>
				<div>Zeremonie</div>
				<!-- 30min. Selfmoderated? -->
			</div>
			<div class="flex flex-row gap-24">
				<div>16:00</div>
				<div>Kaffee und Kuchen</div>
				<!-- Kleinere Torte und Kuchenbuffet -->
			</div>
			<div class="flex flex-row gap-24">
				<div>ab 18:00</div>
				<div>Marroni, Warmer Apfelsaft und Spiele</div>
				<!-- Kürzere, soziale Brettspiele -->
			</div>
		</div>
	</div>

	<div class="mb-24 p-6 text-center text-3xl md:text-5xl">
		<h2 class="mb-8 text-4xl md:text-7xl">Teilnahme</h2>
		<form class="flex flex-col items-start gap-6" action="https://formspree/blabla">
			<div class="flex w-full items-center gap-12">
				<input type="radio" id="yes" name="participation" value="yes" checked />
				<label for="yes">Ja, ich nehme teil</label>
			</div>
			<div class="mb-8 flex w-full items-center gap-12">
				<input type="radio" id="no" name="participation" value="no" />
				<label for="no">Nein, ich nehme nicht teil</label>
			</div>
			<div class="flex w-full items-center justify-between">
				<label for="name">Name</label>
				<input class="border-2 px-4 py-1" type="text" id="name" name="name" />
			</div>
			<div class="mb-8 flex w-full items-center justify-between">
				<label for="email">E-Mail</label>
				<input class="border-2 px-4 py-1" type="email" id="email" name="email" />
			</div>
			<div class="flex w-full justify-center">
				<button type="submit" class="rounded bg-green-900 p-5 text-white hover:bg-green-800"
					>Abschicken</button
				>
			</div>
		</form>
	</div>
</div>
