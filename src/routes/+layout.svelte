<!-- src/routes/+layout.svelte -->
<script>
	import '../app.css';
	let { children } = $props();
</script>

<main class="mx-auto max-w-6xl px-4 font-sans">
	<!-- Navigation -->
	<nav class="flex flex-col items-center justify-between py-6 sm:flex-row">
		<div class="mb-4 flex items-center sm:mb-0">
			<img
				src="/images/logo.jpg"
				alt="The Bean Spot Logo"
				class="mr-3 h-32 w-32 rounded-full object-cover"
			/>
			<p class="text-4xl">The Bean Spot</p>
		</div>
		<div class="flex flex-wrap justify-center gap-4 sm:space-x-8">
			<a href="/" class="text-sm font-medium uppercase">Home</a>
			<a href="/about" class="text-sm font-medium uppercase">About</a>
			<a href="/menu" class="text-sm font-medium uppercase">Menu</a>
			<a href="/contact" class="text-sm font-medium uppercase">Contact</a>
		</div>
	</nav>
	{@render children()}
	<!-- Footer -->
	<footer class="my-8 grid grid-cols-1 gap-4 pb-8 md:grid-cols-3">
		<!-- Contact Info -->
		<div class="border border-gray-300 p-6">
			<h3 class="mb-4 font-medium uppercase">Contact Information</h3>
			<p class="mb-1 text-sm">E: mailhere</p>
			<p class="mb-4 text-sm">info@thebeanspot.com</p>
			<p class="mb-1 text-sm">Phone</p>
			<p class="text-sm">+1 (804) 725-6138</p>
		</div>
		<!-- Map -->
		<div class="relative col-span-1 h-40 bg-gray-200 md:col-span-2">
			<!-- Replace with map -->
			<div class="absolute inset-0"></div>
			<!-- Address overlay -->
			<div class="bg-opacity-70 absolute top-4 left-4 bg-black p-4 text-white">
				<h3 class="mb-2 font-medium uppercase">256 Main St.</h3>
				<p class="mb-2 text-sm">256 Main St., Mathews, VA, United States, Virginia</p>
				<p class="text-sm">Sunday through Thursday</p>
				<p class="text-sm">8:00 AM to 2:00 PM</p>
				<p class="text-sm">Fridays & Saturdays</p>
				<p class="text-sm">8:00 AM to 4:00 PM</p>
			</div>
		</div>
	</footer>
	<!-- Copyright -->
	<div
		class="flex flex-col items-center justify-between border-t border-gray-200 py-4 text-xs sm:flex-row"
	>
		<div>
			<p>Copyright 2020 © The Bean Spot</p>
			<p>Privacy | Privacy statement | Disclaimer</p>
			<p class="mt-4">Inspiration or new possibilities? Contact us!</p>
		</div>
		<!-- Social Media Icons -->
		<div class="mt-4 flex space-x-2 sm:mt-0">
			<!-- Replace with actual social icons -->
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
			<div class="h-6 w-6 rounded-full bg-gray-200"></div>
		</div>
	</div>
</main>
