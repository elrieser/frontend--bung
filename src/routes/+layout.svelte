<script>
	import '../app.css';
	let { children } = $props();
</script>

<div
<<<<<<< HEAD
	class="background-color: rgba( flex min-h-screen flex-col items-center justify-evenly bg-blue-100"
=======
	class="--tw-bg-opacity: 1; background-color: rgba(250, 251, 255, var(--tw-bg-opacity)); flex
min-h-screen flex-col items-center justify-evenly bg-blue-50"
>>>>>>> 25daf470de300f9d6b7adf2c34bd0143ac6bfdf6
>
	{@render children()}
</div>

<div>
	<div class="flex justify-end">
		<div class="flex gap-1">
			<p>Monthly Billing</p>

			<input
				type="checkbox"
				class="toggle border-none bg-white [--tglbg:#a729f5] hover:bg-white
 "
				checked="checked"
			/>

			<p>Yearly Billing</p>
		</div>
	</div>
</div>
