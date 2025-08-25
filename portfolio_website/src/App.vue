<script setup>
import { defineAsyncComponent } from 'vue';
const Navbar = defineAsyncComponent(() => import('./components/Navbar.vue'));
</script>

<template>
	<div class="bg-teal-400 dark:bg-teal-800">
		<Navbar />
	</div>
</template>

<style scoped></style>
