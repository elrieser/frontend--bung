<script>
	import { writable } from 'svelte/store';

	let time = 'month';
	let price = writable(1);
	let sliderValue = 0;

	function switchTime() {
		if (time === 'month') {
			time = 'year';
		} else {
			time = 'month';
		}
		calculatePrice;
	}

	function calculatePrice() {
		let basePrice = sliderValue;
		if (time === 'year') {
			basePrice = basePrice * 12 * 0.75;
		}
	}

	function onSliderChange(event) {
		sliderValue = parseInt(event.target.value);
		price.update(() => {
			let basePrice = sliderValue / 1;
			if (time === 'month') {
				return basePrice > 32 ? 32 : basePrice;
			} else {
				let yearlyPrice = basePrice * 12;
				return yearlyPrice > 384 ? 384 : yearlyPrice;
			}
		});
	}
</script>

<div class="mb-12 mt-16 flex flex-col items-center space-y-8">
	<h1 class="mb-2 text-center text-3xl font-bold">Simple, traffic-based pricing</h1>
	<p class="mb-6 text-center text-sm text-gray-500">
		Sign-up for our 30-day trial. No credit card required.
	</p>

	<div class="flex w-[400px] flex-col items-center space-y-6 rounded-3xl bg-white p-6 shadow-xl">
		<div class="mb-6 flex w-full items-center justify-between">
			<div class="text-center">
				<p class="text-l font-semibold text-gray-500">100K Pageviews</p>
			</div>

			<div class="text-center">
				<p class="text-3xl text-gray-500"><b class="text-black">${$price}</b> / {time}</p>
			</div>
		</div>

		<div class="mb-4 w-full">
			<input
				type="range"
				min="0"
				max="32"
				value={sliderValue}
				class="range range-accent"
				on:input={onSliderChange}
			/>
		</div>

		<div class="flex place-content-center">
			<div class="flex place-self-end">
				<div class="flex gap-1">
					<button
						class="h-4 w-20 place-self-end rounded-xl bg-orange-500 text-[10px] text-orange-200"
						>25% Discount</button
					>
					<p class="text-[10px] text-gray-500">Yearly Billing</p>

					<input type="checkbox" class="toggle toggle-xs" checked="checked" on:click={switchTime} />

					<p class="text-[10px] text-gray-500">Monthly Billing</p>
				</div>
			</div>
		</div>
		<div class="mb-6 flex w-full items-center justify-between">
			<div class="text-[10px] text-gray-500">
				<ul class="list-disc">
					<li>Unlimited websites</li>
					<li>100% data ownership</li>
					<li>Email reports</li>
				</ul>
			</div>
			<div>
				<button class="h-7 w-40 place-self-end rounded-xl bg-black text-xs text-white"
					>Start my trial</button
				>
			</div>
		</div>
	</div>
</div>
