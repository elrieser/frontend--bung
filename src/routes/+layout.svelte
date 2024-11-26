<script>
	import '../app.css';
	let { children } = $props();
</script>

<div
	class="background-color: rgba( flex min-h-screen flex-col items-center justify-evenly bg-blue-100"
>
	{@render children()}
</div>

<div class="flex place-self-end bg-green-50">
	<div class="flex place-self-end">
		<div class="flex gap-1">
			<p>Monthly Billing</p>

			<input
				type="checkbox"
				class="toggle border-none bg-black [--tglbg:#a729f5] hover:bg-white
 "
				checked="checked"
			/>

			<p>Yearly Billing</p>
		</div>
	</div>
</div>
