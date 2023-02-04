<script>
	import { onMount } from 'svelte';

	//on screen sizes smaller than 768px change the src of the image to the mobile version
	onMount(() => {
		const image = document.querySelector('img');
		const mediaQuery = window.matchMedia('(max-width: 768px)');
		const changeImage = (e) => {
			if (e.matches) {
				image.src = '/images/image-product-mobile.jpg';
			} else {
				image.src = '/images/image-product-desktop.jpg';
			}
		};
		mediaQuery.addEventListener('change', changeImage);
		changeImage(mediaQuery);
	});
</script>

<svelte:head>
	<title>Product Preview Card</title>
	<link rel="icon" type="image/png" href="/favicon-32x32.png" />
</svelte:head>

<main class="flex justify-center items-center w-screen h-screen -md:h-max -md:my-20 bg-cream">
	<div class="flex w-[700px] h-[500px] -md:block -md:w-[300px]">
		<div class="overflow-hidden rounded-l-xl -md:w-[300px] -md:rounded-l-none -md:rounded-t-xl">
			<img src="/images/image-product-desktop.jpg" class="" alt="Top down of a bottle of perfume" />
		</div>
		<div
			class="bg-white rounded-r-xl -md:rounded-r-none -md:rounded-b-xl p-8 flex flex-col justify-end w-[400px] -md:w-[300px]"
		>
			<p class="tracking-[0.3em] font-montserrat text-dark-grayish-blue text-xs mb-4">PERFUME</p>
			<h2 class="font-fraunces text-3xl text-very-dark-blue mb-6">
				Gabrielle<br />
				Essence Eau<br />
				De Parfum
			</h2>
			<p class="text-dark-grayish-blue font-montserrat text-sm mb-auto">
				A floral, solar and voluptuous interpretation composed by Olivier Polge, Perfumer-Creator
				for the House of CHANEL.
			</p>
			<div class="flex gap-4 items-center mb-8">
				<p class="text-dark-cyan font-fraunces text-4xl">$149.99</p>
				<p class="text-dark-grayish-blue font-montserrat text-sm line-through">$169.99</p>
			</div>
			<button
				class="font-montserrat bg-dark-cyan rounded-md text-white gap-3 items-center py-3 px-12 w-fit flex"
				><svg width="15" height="16" xmlns="http://www.w3.org/2000/svg"
					><path
						d="M14.383 10.388a2.397 2.397 0 0 0-1.518-2.222l1.494-5.593a.8.8 0 0 0-.144-.695.8.8 0 0 0-.631-.28H2.637L2.373.591A.8.8 0 0 0 1.598 0H0v1.598h.983l1.982 7.4a.8.8 0 0 0 .799.59h8.222a.8.8 0 0 1 0 1.599H1.598a.8.8 0 1 0 0 1.598h.943a2.397 2.397 0 1 0 4.507 0h1.885a2.397 2.397 0 1 0 4.331-.376 2.397 2.397 0 0 0 1.12-2.021ZM11.26 7.99H4.395L3.068 3.196h9.477L11.26 7.991Zm-6.465 6.392a.8.8 0 1 1 0-1.598.8.8 0 0 1 0 1.598Zm6.393 0a.8.8 0 1 1 0-1.598.8.8 0 0 1 0 1.598Z"
						fill="#FFF"
					/></svg
				> Add to Cart</button
			>
		</div>
	</div>
</main>
