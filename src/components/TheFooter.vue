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
				<li v-for="(f, i) in follow" :key="i" class="mr-3">
					<a
						:href="`https://${f.toLowerCase()}.com/karimdxy`"
						target="_blank"
						class="text-white hover:text-white hover:underline"
						v-text="f"
					>
					</a>
				</li>
				<li class="mr-3">
					<a
						href="https://t.me/karimdxy"
						target="_blank"
						class="text-white hover:text-white hover:underline"
					>
						Telegram
					</a>
				</li>
				<li class="mr-3">
					<a
						href="https://linkedin.com/in/karimdxy"
						target="_blank"
						class="text-white hover:text-white hover:underline"
					>
						LinkedIn
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
		follow: ["Twitter", "Facebook", "Github"]
	})
};
</script>
