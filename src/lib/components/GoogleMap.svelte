<script>
	import { onMount } from 'svelte';
	import { PUBLIC_GOOGLE_MAPS_API_KEY } from '$env/static/public';

	export let address = '256 Main St., Mathews, VA, United States';
	export let zoom = 15;
	let mapElement;

	onMount(() => {
		// Load Google Maps API script
		const script = document.createElement('script');
		script.id = 'google-maps-script';

		script.src = `https://maps.googleapis.com/maps/api/js?key=${PUBLIC_GOOGLE_MAPS_API_KEY}&loading=async&callback=initMap`;
		script.async = true;
		script.defer = true;

		// Define the callback function globally
		window.initMap = () => {
			const geocoder = new google.maps.Geocoder();

			geocoder.geocode({ address }, (results, status) => {
				console.log(results, status);
				if (status === 'OK' && results[0]) {
					const location = results[0].geometry.location;

					// Create an offset point for the center - shift slightly west
					// This will make the map appear shifted to the right
					const offsetPoint = {
						lat: location.lat(),
						lng: location.lng() - 0.008 // Adjust this value as needed
					};

					// Initialize map with the offset center
					const map = new google.maps.Map(mapElement, {
						center: offsetPoint, // Use offset point instead of actual location
						zoom: zoom
					});

					const marker = new google.maps.Marker({
						map: map,
						position: results[0].geometry.location
					});
				} else {
					console.error(`Geocoding failed: ${status}`);
				}
			});
		};

		document.head.appendChild(script);
	});
</script>

<div bind:this={mapElement} class="absolute inset-0"></div>
