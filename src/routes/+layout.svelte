<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class="min-h-screen px-8 my-10">
	{@render children()}
</div>
