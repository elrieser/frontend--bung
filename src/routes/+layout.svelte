<script>
	import '../app.css';
	let { children } = $props();
</script>

<div class="flex min-h-screen flex-col items-center justify-evenly bg-red-500">
	{@render children()}
</div>
