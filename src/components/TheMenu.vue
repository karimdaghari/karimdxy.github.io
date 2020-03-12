<template>
	<div class="flex justify-center">
		<li class="mr-8 mb-6 lg:mb-0">
			<g-link to="/" class="text-copy-primary hover:text-gray-600">
				About
			</g-link>
		</li>
		<li>
			<g-link to="/blog" class="text-copy-primary hover:text-gray-600">
				Blog
			</g-link>
		</li>
		<li class="ml-6 mr-8 mb-6 lg:mb-0">
			<theme-switcher :theme="theme" @themeChanged="changeTheme" />
		</li>
	</div>
</template>

<script>
import ThemeSwitcher from "@/components/ThemeSwitcher";
export default {
	name: "Menu",
	components: {
		ThemeSwitcher
	},
	props: {
		theme: {
			type: String
		}
	},
	methods: {
		changeTheme(theme) {
			this.$emit("change-theme", theme);
		}
	}
};
</script>
