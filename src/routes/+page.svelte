<script>
	import { writable } from 'svelte/store';

	let time = 'month';
	let pricel = writable(1);
	let price = 1;

	function switchTime() {
		if (time === 'month') {
			time = 'year';
			price = price * 12;
		} else {
			time = 'month';
			price = price / 12;
		}
	}

	function ChangePrice() {
		pricel.update((n) => {
			if (n + 1 > 32) {
				return 32;
			} else if (n + 1 > 384) {
				return 384;
			} else {
				return n + 1;
			}
		});
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
			<p>$ {price} /{time}</p>
		</div>
		<div class="w-[400px] place-self-center">
			<input type="range" min="0" max="100" value="40" class="range range-accent" />
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
