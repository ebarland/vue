<template>
	<button @click="toggle" :aria-pressed="isDark" title="Toggle dark mode"
		class="p-2 rounded-full hover:ring-2 hover:ring-offset-2 hover:ring-blue-500 transition">
		<Icon v-if="isDark" icon="line-md:sunny-outline-to-moon-loop-transition" </Icon>
			<Icon v-else icon="line-md:moon-to-sunny-outline-loop-transition" </Icon>
	</button>
</template>

<script setup>
import { ref } from 'vue';
const isDark = ref(document.documentElement.classList.contains("dark"));
const STORAGE_KEY = "theme"; // 'dark' || 'light'

const apply = (wantDark) => {
	document.documentElement.classList.toggle("dark", wantDark);
	isDark.value = wantDark;
};

const toggle = () => {
	const next = !isDark.value;
	apply(next);
	try {
		localStorage.setItem(STORAGE_KEY, next ? "dark" : "light");
	}
	catch { console.log("Failed to store theme to the local storage"); }
};
</script>
