<template>
	<g-link v-if="theme === 'theme-light'" to="/">
		<g-image src="../../static/logo.svg" class="w-40" alt="logo" />
	</g-link>
	<g-link v-else to="/">
		<g-image src="../../static/logo_dark_mode.svg" class="w-40" alt="logo" />
	</g-link>
</template>

<script>
export default {
	props: {
		theme: {
			type: String
		}
	}
};
</script>

<style></style>
