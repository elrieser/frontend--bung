<script>
	import '../app.css';
	let { children } = $props();
</script>

<div
	class="--tw-bg-opacity: 1; background-color: rgba(250, 251, 255, var(--tw-bg-opacity)); flex
min-h-screen flex-col items-center justify-evenly bg-blue-50"
>
	{@render children()}
</div>
