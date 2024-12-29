<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="bg-amber-100">
	{@render children()}
</div>
