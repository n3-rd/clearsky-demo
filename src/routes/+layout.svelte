<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="root-layout">
	<main>{@render children()}</main>
</div>
