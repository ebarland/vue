<script setup>
import { ref } from "vue";
const links = ref(["http://vg.no", "http://sigint.no"])
</script>

<template>
	<aside class="bg-gray-800 px-4 py-4 md:row-span-2">
		<ul class="space-y-3">
			<li class="text-red-500" v-for="link in links" :key="link">
				<a :href="link" target="_blank" rel="noopener norefferer">{{ link }}</a>
			</li>
		</ul>
	</aside>
</template>
