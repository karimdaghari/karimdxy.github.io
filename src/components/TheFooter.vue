<template>
	<footer class="bg-green-700 text-white">
		<div
			class="container mx-auto flex flex-col lg:flex-row items-center justify-between py-8"
		>
			<div class="mb-8 lg:mb-0">
				<div>&copy; {{ new Date().getFullYear() }}</div>
				<div class="hidden">
					<a href="/rss.xml" class="text-white hover:text-gray-400 font-normal"
						>RSS Feed</a
					>
					|
					<a
						href="/sitemap.xml"
						class="text-white hover:text-gray-400 font-normal"
					>
						Sitemap
					</a>
				</div>
			</div>
			<ul class="flex items-center">
				<li v-for="f in follow" :key="f.name" class="mr-3">
					<a
						:href="
							`https://${f.name.toLowerCase()}.com/${f.prefix || ''}karimdxy`
						"
						target="_blank"
						class="text-white hover:text-white hover:underline"
					>
						{{ f.name }}
					</a>
				</li>
			</ul>
		</div>
	</footer>
</template>

<script>
export default {
	name: "Footer",
	data: () => ({
		follow: [
			{
				name: "Twitter"
			},
			{
				name: "Telegram"
			},
			{
				name: "Facebook"
			},
			{
				name: "LinkedIn",
				prefix: "in/"
			}
		]
	})
};
</script>
