<template>
	<Layout>
		<div
			class="hero container-inner mx-auto flex flex-col sm:flex-row justify-between py-16"
		>
			<div class="text-4xl font-bold w-full sm:w-3/5 text-center sm:text-left">
				<div class="leading-tight">Hey there 👋🏻</div>
				<div class="text-green-700 leading-tight">
					I'm Karim, a fullstack JS dev and the maker of
					<a
						href="https://eggnite.xyz"
						target="_blank"
						rel="noopener noreferrer"
						class="text-orange hover:text-orange"
					>
						eggnite</a
					>.
				</div>
			</div>
			<div class="mt-8 sm:mt-0">
				<g-image
					src="../../static/developer.svg"
					alt="hero"
					class="mx-auto sm:mx-0"
				/>
			</div>
		</div>
		<!-- end hero -->

		<div class="container-inner mx-auto mb-10">
			<p class="text-lg sm:text-xl">
				Welcome to my humble demeure, this is my little corner of the internet.
				I write about things I care about.
			</p>
		</div>
	</Layout>
</template>

<script>
export default {
	metaInfo: {
		title: "Home"
	}
};
</script>
