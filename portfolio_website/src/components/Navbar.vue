<script setup>
import { ref } from 'vue';
import ThemeToggle from './ThemeToggle.vue';
const isMenuOpen = ref(false);
const menu = ref([
	{ name: 'Services', href: '#services' },
	{ name: 'Skills', href: '#skills' },
	{ name: 'Why me', href: '#whyme' },
	{ name: 'Projects', href: '#projects' },
	{ name: 'Contact', href: '#contact' }
]);

const scrollToSection = (href) => {
	isMenuOpen.value = false;
	const section = document.querySelector(href);
	if (section) {
		section.scrollToSection({ behavior: 'smooth' });
	}
};
</script>

<template>
	<header>
		<div class="
			flex <!-- Turns this into a flex container. -->
			justify-between <!-- A flexbox property.  → Pushes children to the far left and right, with space in between. -->
			items-center <!-- Another flexbox property. → Aligns children vertically in the center of the row. → Without this, things could “hug” the top/bottom unevenly.-->
			p-6 lg:px-10
			relative <!-- relative → Puts the element into relative positioning mode. This doesn’t move it, but allows child elements to use positioning (like absolute, fixed) relative to this container. -->
			z-20 <!-- basically a z-buffer. higher numbers float above lower numbers-->">

			<div class="text-3xl font-bold text-black dark:text-white">LOGO</div>

			<!--Mobile toggle btn-->
			<div class="md:hidden z-30">
				<button class="block focus:outline-none" @click="isMenuOpen = !isMenuOpen">
					<span v-if="isMenuOpen" class="text-5xl text-black dark:text-white">
						<Icon icon='material-symbols:close' class="text-black"></Icon>
					</span>
					<span v-else class="text-5xl text-black dark:text-white">
						<Icon icon='material-symbols:menu' class="text-black"></Icon>
					</span>
				</button>
			</div>

			<!-- Navbar link -->
			<nav class="fixed inset-0 z-20 flex flex-col items-center justify-center bg-primary 
					   md:relative md:bg-transparent md:flex md:justify-between md:flex-row"
				:class="[isMenuOpen ? 'block' : 'hidden']">

				<ul class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0">
					<li v-for="item in menu" :key="item.name">
						<a :href="item.href"
							class="block transition ease-linear md:text-lg lg:text-xl font-bold text-black hover:text-purple-300 dark:text-white dark:hover:text-violet-500"
							@click="scrollToSection(item.href)">
							{{ item.name }}
						</a>
					</li>
				</ul>

				<ThemeToggle class="text-black dark:text-white text-3xl md:ml-20 mt-5 md:mt-0" />
			</nav>

		</div>
	</header>
</template>
