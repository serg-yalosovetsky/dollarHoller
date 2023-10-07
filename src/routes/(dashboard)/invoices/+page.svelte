<script>
	import CircledAmount from './../../../lib/components/CircledAmount.svelte';
	import ThreeDots from './../../../lib/components/Icon/ThreeDots.svelte';
	import View from '$lib/components/Icon/View.svelte';
	import Search from '$lib/components/Search.svelte';
	import Tag from '$lib/components/Tag.svelte';
</script>

<svelte:head><title>Invoices | DollarHoller</title></svelte:head>

<div class="flex justify-between items-center mb-16">
	<!-- search field -->
	<Search />

	<!-- new invoice button -->
	<div>
		<button
			class="relative whitespace-nowrap rounded-lg bg-lavenderIndigo px-10 py-3 font-sansSerif text-xl font-black text-white shadow-colored hover:shadow-coloredHover translate-y-0 hover:-translate-y-2 transition-all"
			>+ Invoice</button
		>
	</div>
</div>

<!-- list of invoices -->
<div>
	<!-- header -->
	<div class=" text-daisyBush invoice-table table-header">
		<h3>Staus</h3>
		<h3>Due date</h3>
		<h3>ID</h3>
		<h3>Client</h3>
		<h3>Amount</h3>
	</div>

	<!-- invoices -->
	<div class="invoice-table invoice-row items-center bg-white py-6 rounded-lg shadow-tableRow">
		<div><Tag label="late" /></div>
		<div class="text-lg">8/1/2022</div>
		<div class="text-lg">12345</div>
		<div class="text-xl font-bold">Compressed.fm</div>
		<div class="text-lg font-mono font-bold">$504.00</div>
		<div class="text-lg center"><a class="text-pastelPurple hover:text-daisyBush" href="/#"><View /></a></div>
		<div class="text-lg center"><button class="text-pastelPurple hover:text-daisyBush"><ThreeDots /></button></div>
	</div>
</div>

<div><CircledAmount label="Total" amount="1,144.00" /></div>

<!-- <div>Total: $1,144.00</div> -->

<style lang="postcss">
	.table-header h3 {
		@apply text-xl font-black leading-snug;
	}

	.invoice-row {
		grid-template-areas: 'status dueDate invoiceNumber clientName amount viewButton moreButton';
	}
</style>
