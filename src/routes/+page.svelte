<script>
	import { writable } from 'svelte/store';

	let time = 'month';
	let price = writable(1);
	let sliderValue = 1;

	function switchTime() {
		if (time === 'month') {
			time = 'year';
		} else {
			time = 'month';
		}
		calculatePrice;
	}

	function calculatePrice() {
		let basePrice = 1;
		if (time === 'year') {
			basePrice = basePrice * 12 * 0.75;
		}
		price.set(basePrice.toFixed(2));
	}

	function onSliderChange(event) {
		sliderValue = event.target.value;
		calculatePrice;
	}
</script>

<div class="flex flex-col items-center">
	<h1 class="text-3xl font-semibold">Simple, traffic-based pricing</h1>
	<p class="text-sx">Sign-up for our 30-day trial. No credit card required.</p>
</div>

<div class="flex h-[300px] w-[500px] flex-col items-center justify-evenly rounded-md bg-white">
	<div>
		<p>100K Pageviews</p>
		<div>
			<p><b>$ {$price} </b>/{time}</p>
		</div>
		<div class="w-[400px] place-self-center">
			<input
				type="range"
				min="0"
				max="100"
				value="40"
				class="range range-accent"
				on:input={onSliderChange}
			/>
		</div>
		<div class="flex place-content-center">
			<div class="flex place-self-end">
				<div class="flex gap-1">
					<p class="text-xs">Yearly Billing</p>

					<input
						type="checkbox"
						class="toggle toggle-xs bg-white"
						checked="checked"
						on:click={switchTime}
					/>

					<p class="text-xs">Monthly Billing</p>
				</div>
			</div>
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
</div>
