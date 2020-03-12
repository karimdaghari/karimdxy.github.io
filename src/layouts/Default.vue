<template>
	<div
		class="content-wrapper bg-background-primary font-sans text-copy-primary leading-normal flex flex-col min-h-screen"
		:class="theme"
	>
		<header class="border-t-14 border-green-700">
			<nav
				class="container mx-auto flex flex-wrap justify-between items-center py-8"
			>
				<div>
					<TheLogo :theme="theme" />
				</div>
				<div class="block lg:hidden">
					<button
						@click="toggle"
						class="flex items-center px-3 py-2 border rounded border-gray-500 hover:text-gray-600 hover:border-gray-600"
					>
						<svg
							class="current-color h-3 w-3"
							viewBox="0 0 20 20"
							xmlns="http://www.w3.org/2000/svg"
						>
							<path
								d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"
								fill="gray"
							/>
						</svg>
					</button>
				</div>
				<ul
					class="uppercase tracking-wide font-bold w-full block flex-grow lg:flex lg:flex-initial lg:w-auto items-center mt-8 lg:mt-0"
					:class="isOpen ? 'block' : 'hidden'"
				>
					<li class="ml-3 sm:ml-0 mr-8 mb-6 lg:mb-0">
						<search-input />
					</li>
					<TheMenu :theme="theme" @change-theme="updateTheme" />
				</ul>
			</nav>
		</header>

		<div class="flex-grow">
			<slot />
		</div>
		<TheFooter />
		<div style="display:none">
			<svg
				id="dots-triangle"
				width="170"
				height="170"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					d="M168.152 170a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm-18.478-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm-18.478 0a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.479a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm-18.479 0a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zM94.24 133.043a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm-18.478 36.956a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm-18.478 55.434a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.479a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm-18.479 73.913a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.479a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm-18.478 92.391a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0 18.479a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.479a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zM1.848 133.044a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.695zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0 18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-55.435a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.479a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.695 1.848 1.848 0 0 1 0 3.695zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696zm0-18.478a1.848 1.848 0 1 1 0-3.696 1.848 1.848 0 0 1 0 3.696z"
					fill="#2C8056"
					fill-rule="evenodd"
					opacity=".503"
				/>
			</svg>
		</div>
	</div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import SearchInput from "../components/SearchInput";
import TheMenu from "@/components/TheMenu";
import TheFooter from "@/components/TheFooter";
import TheLogo from "@/components/TheLogo";

export default {
	components: {
		SearchInput,
		TheMenu,
		TheFooter,
		TheLogo
	},
	mounted() {
		this.theme = localStorage.getItem("theme") || "theme-light";
	},
	data() {
		return {
			isOpen: false,
			theme: ""
		};
	},
	methods: {
		toggle() {
			this.isOpen = !this.isOpen;
		},
		updateTheme(theme) {
			this.theme = theme;
		}
	}
};
</script>

<style src="../css/main.css" />
