<script setup>
import Navbar from './components/Navbar.vue';
import Sidebar from './components/Sidebar.vue';
</script>

<template>
	<div class="grid min-h-screen grid-rows-[auto_1fr_auto] grid-cols-1 md:grid-cols-[200px_1fr]">
		<Navbar />
		<Sidebar />

		<main class="p-6">
			<h2 class="text-xl font-semibold mb-4">Welcome</h2>
			<p>This is the main content area. Resize the screen and watch it scale.</p>
		</main>

		<footer class="bg-indigo-900 text-white col-span-1 md:col-span-2 flex justify-center items-center p-4">
			© 2025 My App
		</footer>
	</div>
</template>
