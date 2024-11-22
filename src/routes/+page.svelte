<script>
	import '../style.css';
</script>

<div class="flex flex-col items-center">
	<h1 class="text-3xl font-semibold">Simple, traffic-based pricing</h1>
	<p>Sign-up for our 30-day trial. No credit card required.</p>
</div>

<div class="h-[300px] w-[500px] rounded-md bg-white">
	<p>100K Pageviews</p>
	<div class="w-[400px] place-self-center">
		<input type="range" min="0" max="100" value="40" class="range range-xs" />
	</div>
	<div class="place-content-end text-xs">
		<ul class="list-disc">
			<li>Unlimited websites</li>
			<li>100% data ownership</li>
			<li>Email reports</li>
		</ul>
	</div>
	<button class="h-5 w-20 place-self-end rounded-xl bg-black text-xs text-white"
		>Start my trial</button
	>
</div>
