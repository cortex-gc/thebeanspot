<!-- src/routes/contact/+page.svelte -->
<script>
	// Form handling logic
	let name = '';
	let email = '';
	let subject = '';
	let message = '';
	let submitted = false;

	// Social media links
	const socialLinks = [
		{ name: 'Facebook', url: 'https://facebook.com/thebeanspot' },
		{ name: 'Instagram', url: 'https://instagram.com/thebeanspot' },
		{ name: 'Twitter', url: 'https://twitter.com/thebeanspot' }
	];

	// Handle form submission
	function handleSubmit() {
		// In a real application, you would send the form data to a server
		// For now, we'll just simulate a successful submission
		submitted = true;

		// Reset form fields
		setTimeout(() => {
			name = '';
			email = '';
			subject = '';
			message = '';
			submitted = false;
		}, 3000);
	}
</script>

<div class="py-8">
	<!-- Page Title -->
	<div class="mb-12 text-center">
		<h1 class="text-4xl font-medium">Contact Us</h1>
		<div class="mx-auto mt-3 h-1 w-20 bg-black"></div>
	</div>

	<!-- Contact Information and Form -->
	<div class="mb-16 grid grid-cols-1 gap-8 md:grid-cols-3">
		<!-- Contact Information Column -->
		<div>
			<div class="mb-8">
				<h2 class="mb-4 text-xl font-medium">Visit Our Shop</h2>
				<p class="mb-1">256 Main St.</p>
				<p class="mb-4">Mathews, VA, United States</p>

				<h3 class="mb-2 font-medium">Hours</h3>
				<p class="mb-1">Sunday - Thursday: 8:00 AM to 2:00 PM</p>
				<p class="mb-4">Friday & Saturday: 8:00 AM to 4:00 PM</p>
			</div>

			<div class="mb-8">
				<h2 class="mb-4 text-xl font-medium">Get In Touch</h2>
				<p class="mb-1">Phone: +1 (804) 725-6138</p>
				<p class="mb-4">Email: info@mainstreetmatthews.biz</p>
			</div>

			<div>
				<h2 class="mb-4 text-xl font-medium">Follow Us</h2>
				<div class="flex flex-wrap gap-4">
					{#each socialLinks as social}
						<a
							href={social.url}
							target="_blank"
							rel="noopener noreferrer"
							class="flex h-10 w-10 items-center justify-center rounded-full bg-black text-white transition-colors hover:bg-gray-800"
						>
							<!-- Placeholder for social icon -->
							<span class="text-xs">{social.name.charAt(0)}</span>
						</a>
					{/each}
				</div>
			</div>
		</div>

		<!-- Contact Form Column -->
		<div class="md:col-span-2">
			<h2 class="mb-6 text-xl font-medium">Send Us a Message</h2>

			{#if submitted}
				<div class="mb-6 rounded border border-green-400 bg-green-100 px-4 py-3 text-green-700">
					<p>Thank you for your message! We'll get back to you soon.</p>
				</div>
			{/if}

			<form on:submit|preventDefault={handleSubmit} class="space-y-6">
				<div class="grid grid-cols-1 gap-6 sm:grid-cols-2">
					<div>
						<label for="name" class="mb-2 block text-sm font-medium">Your Name</label>
						<input
							type="text"
							id="name"
							bind:value={name}
							required
							class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"
						/>
					</div>

					<div>
						<label for="email" class="mb-2 block text-sm font-medium">Your Email</label>
						<input
							type="email"
							id="email"
							bind:value={email}
							required
							class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"
						/>
					</div>
				</div>

				<div>
					<label for="subject" class="mb-2 block text-sm font-medium">Subject</label>
					<input
						type="text"
						id="subject"
						bind:value={subject}
						required
						class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"
					/>
				</div>

				<div>
					<label for="message" class="mb-2 block text-sm font-medium">Message</label>
					<textarea
						id="message"
						bind:value={message}
						rows="6"
						required
						class="w-full border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"
					></textarea>
				</div>

				<button
					type="submit"
					class="bg-black px-6 py-3 text-sm font-medium text-white uppercase transition-colors hover:bg-gray-800"
				>
					Send Message
				</button>
			</form>
		</div>
	</div>

	<!-- FAQ Section -->
	<div class="mb-16">
		<div class="mb-8 text-center">
			<h2 class="text-2xl font-medium">Frequently Asked Questions</h2>
			<div class="mx-auto mt-3 h-1 w-20 bg-black"></div>
		</div>

		<div class="grid grid-cols-1 gap-6 md:grid-cols-2">
			<div class="border border-gray-200 p-6">
				<h3 class="mb-2 font-medium">Do you offer catering services?</h3>
				<p class="text-sm">
					Yes, we offer catering for events of all sizes. Please contact us at least 48 hours in
					advance to discuss your requirements and place an order.
				</p>
			</div>

			<div class="border border-gray-200 p-6">
				<h3 class="mb-2 font-medium">Are you hiring?</h3>
				<p class="text-sm">
					We're always looking for passionate baristas and team members. Please bring your resume to
					the shop or email it to our contact address.
				</p>
			</div>

			<div class="border border-gray-200 p-6">
				<h3 class="mb-2 font-medium">Do you sell gift cards?</h3>
				<p class="text-sm">
					Yes, gift cards are available in-store in any denomination. They make perfect gifts for
					the coffee lovers in your life!
				</p>
			</div>

			<div class="border border-gray-200 p-6">
				<h3 class="mb-2 font-medium">Do you offer Wi-Fi?</h3>
				<p class="text-sm">
					Yes, we provide free Wi-Fi for all our customers. Ask our baristas for the current
					password when you visit.
				</p>
			</div>
		</div>
	</div>

	<!-- Newsletter Signup -->
	<div class="mb-16 bg-gray-100 p-8 text-center">
		<h2 class="mb-4 text-2xl font-medium">Stay Updated</h2>
		<p class="mx-auto mb-6 max-w-lg">
			Subscribe to our newsletter for updates on seasonal drinks, events, and special promotions.
		</p>

		<form class="mx-auto flex max-w-md flex-col gap-4 sm:flex-row">
			<input
				type="email"
				placeholder="Your email address"
				class="flex-grow border border-gray-300 px-4 py-2 focus:border-black focus:outline-none"
				required
			/>
			<button
				type="submit"
				class="bg-black px-6 py-2 text-sm font-medium text-white uppercase transition-colors hover:bg-gray-800"
			>
				Subscribe
			</button>
		</form>
	</div>
</div>
