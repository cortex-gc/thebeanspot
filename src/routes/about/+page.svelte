<!-- src/routes/about/+page.svelte -->
<script>
	// No special logic needed for this page
</script>

<div class="py-8">
	<!-- Page Title -->
	<div class="mb-12 text-center">
		<h1 class="text-4xl font-medium">About The Bean Spot</h1>
		<div class="mx-auto mt-3 h-1 w-20 bg-black"></div>
	</div>

	<!-- Our Story Section -->
	<div class="mb-16 grid grid-cols-1 gap-8 md:grid-cols-2">
		<div>
			<h2 class="mb-6 text-2xl font-medium">Our Story</h2>
			<p class="mb-4">
				The Bean Spot was founded in 2018 with a simple mission: to create a warm, welcoming space
				where the Mathews community could gather and enjoy exceptional coffee.
			</p>
			<p class="mb-4">
				What started as a small passion project has grown into a beloved local institution, serving
				not just coffee but also fostering connections and community.
			</p>
			<p>
				We believe coffee is more than just a beverage - it's a moment of pause in a busy day, a
				catalyst for conversation, and sometimes, the perfect companion to a good book or productive
				work session.
			</p>
		</div>
		<div class="h-64 bg-gray-200"></div>
	</div>

	<!-- Meet Our Team Section -->
	<div class="mb-16">
		<div class="mb-10 text-center">
			<h2 class="text-2xl font-medium">Meet Our Team</h2>
			<div class="mx-auto mt-3 h-1 w-20 bg-black"></div>
		</div>

		<div class="grid grid-cols-1 gap-10 sm:grid-cols-2 lg:grid-cols-3">
			<!-- Team Member 1 -->
			<div class="flex flex-col items-center text-center">
				<div class="mb-5 h-40 w-40 rounded-full bg-gray-200" style="display: block;"></div>
				<h3 class="mb-1 font-medium">Kevin Farrells</h3>
				<p class="mb-2 text-sm text-gray-600">Owner & Head Barista</p>
				<p class="max-w-xs text-sm">
					Coffee enthusiast with over 10 years of experience in specialty coffee. Kevin is the heart
					and soul of The Bean Spot.
				</p>
			</div>

			<!-- Team Member 2 -->
			<div class="flex flex-col items-center text-center">
				<div class="mb-5 h-40 w-40 rounded-full bg-gray-200"></div>
				<h3 class="mb-1 font-medium">Michael Chen</h3>
				<p class="mb-2 text-sm text-gray-600">Master Roaster</p>
				<p class="max-w-xs text-sm">
					With a background in chemistry and a passion for perfect roasts, Michael ensures our beans
					are always at their flavorful best.
				</p>
			</div>

			<!-- Team Member 3 -->
			<div class="flex flex-col items-center text-center">
				<div class="mb-5 h-40 w-40 rounded-full bg-gray-200"></div>
				<h3 class="mb-1 font-medium">Emily Rodriguez</h3>
				<p class="mb-2 text-sm text-gray-600">Pastry Chef</p>
				<p class="max-w-xs text-sm">
					Emily creates all our delicious in-house pastries and treats, perfectly complementing our
					coffee offerings.
				</p>
			</div>
		</div>
	</div>
</div>
