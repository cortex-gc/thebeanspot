<!-- src/routes/menu/+page.svelte -->
<script>
	// Menu data as JSON array
	const menuItems = [
		// Espresso
		{
			id: 1,
			name: 'Espresso',
			price: 3.25,
			description: 'Our signature blend, rich and bold with notes of chocolate and hazelnut',
			category: 'Espresso'
		},
		{
			id: 2,
			name: 'Americano',
			price: 3.75,
			description: 'Espresso with hot water, smooth and flavorful',
			category: 'Espresso'
		},
		{
			id: 3,
			name: 'Macchiato',
			price: 4.0,
			description: 'Espresso with a dollop of foamed milk',
			category: 'Espresso'
		},

		// Drip Coffee
		{
			id: 4,
			name: 'House Blend',
			price: 2.75,
			largeprice: 3.25,
			description: 'Our medium roast with balanced acidity and full body',
			category: 'Drip Coffee'
		},
		{
			id: 5,
			name: 'Dark Roast',
			price: 2.75,
			largeprice: 3.25,
			description: 'Bold and smoky with a hint of caramel sweetness',
			category: 'Drip Coffee'
		},
		{
			id: 6,
			name: 'Single Origin',
			price: 3.5,
			largeprice: 4.0,
			description: 'Rotating selection of single-origin coffees from around the world',
			category: 'Drip Coffee'
		},

		// Milk-Based
		{
			id: 7,
			name: 'Cappuccino',
			price: 4.5,
			description: 'Equal parts espresso, steamed milk, and foam',
			category: 'Milk-Based'
		},
		{
			id: 8,
			name: 'Latte',
			price: 4.75,
			description: 'Espresso with steamed milk and a light layer of foam',
			category: 'Milk-Based'
		},
		{
			id: 9,
			name: 'Flat White',
			price: 4.5,
			description: 'Espresso with velvety microfoam',
			category: 'Milk-Based'
		},
		{
			id: 10,
			name: 'Mocha',
			price: 5.25,
			description: 'Espresso with chocolate and steamed milk',
			category: 'Milk-Based'
		},

		// Cold Coffee
		{
			id: 11,
			name: 'Cold Brew',
			price: 4.5,
			description: 'Steeped for 18 hours, smooth and refreshing',
			category: 'Cold Coffee'
		},
		{
			id: 12,
			name: 'Iced Latte',
			price: 4.75,
			description: 'Espresso with cold milk over ice',
			category: 'Cold Coffee'
		},
		{
			id: 13,
			name: 'Iced Americano',
			price: 3.75,
			description: 'Espresso with cold water over ice',
			category: 'Cold Coffee'
		}
	];

	// Pastry data
	const pastryItems = [
		{
			id: 1,
			name: 'Chocolate Croissant',
			price: 4.25,
			description: 'Flaky croissant with dark chocolate'
		},
		{
			id: 2,
			name: 'Blueberry Muffin',
			price: 3.75,
			description: 'Made with local berries and lemon zest'
		},
		{
			id: 3,
			name: 'Cinnamon Roll',
			price: 4.5,
			description: 'With our signature cream cheese frosting'
		},
		{
			id: 4,
			name: 'Banana Bread',
			price: 3.5,
			description: 'Classic recipe with walnuts'
		}
	];

	// Featured drink
	const featuredDrink = {
		name: 'Lavender Honey Latte',
		price: 5.75,
		description:
			'Our signature spring drink combines house-made lavender syrup, local honey, our award-winning espresso, and silky steamed milk. Topped with a sprinkle of culinary lavender for a truly memorable coffee experience.'
	};

	// Get unique categories
	const categories = [...new Set(menuItems.map((item) => item.category))];
</script>

<div class="py-8">
	<!-- Page Title -->
	<div class="mb-12 text-center">
		<h1 class="text-4xl font-medium">Our Menu</h1>
		<div class="mx-auto mt-3 h-1 w-20 bg-black"></div>
	</div>

	<!-- Menu Tabs -->
	<div class="mb-16">
		<!-- Coffee Menu Section -->
		<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
			<!-- Left Column -->
			<div>
				{#each categories.slice(0, Math.ceil(categories.length / 2)) as category}
					<div class="mb-10">
						<h2 class="mb-4 border-b border-gray-200 pb-2 text-xl font-medium">{category}</h2>

						{#each menuItems.filter((item) => item.category === category) as item}
							<div class="mb-4">
								<div class="mb-1 flex justify-between">
									<h3 class="font-medium">{item.name}</h3>
									<span class="font-medium">
										${item.price.toFixed(2)}
										{#if item.largeprice}
											/ ${item.largeprice.toFixed(2)}
										{/if}
									</span>
								</div>
								<p class="text-sm text-gray-600">
									{item.description}
								</p>
							</div>
						{/each}
					</div>
				{/each}
			</div>

			<!-- Right Column -->
			<div>
				{#each categories.slice(Math.ceil(categories.length / 2)) as category}
					<div class="mb-10">
						<h2 class="mb-4 border-b border-gray-200 pb-2 text-xl font-medium">{category}</h2>

						{#each menuItems.filter((item) => item.category === category) as item}
							<div class="mb-4">
								<div class="mb-1 flex justify-between">
									<h3 class="font-medium">{item.name}</h3>
									<span class="font-medium">
										${item.price.toFixed(2)}
										{#if item.largeprice}
											/ ${item.largeprice.toFixed(2)}
										{/if}
									</span>
								</div>
								<p class="text-sm text-gray-600">
									{item.description}
								</p>
							</div>
						{/each}
					</div>
				{/each}
			</div>
		</div>
	</div>
</div>
