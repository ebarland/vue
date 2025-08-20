<script setup></script>

<template>
	<ul class="bg-violet-200 w-full border-2 border-violet-600 rounded-md my-4 p-1 md:p-20">
		<li class="text-center font-mono font-extrabold text-[30px]">kneegrow</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
		<li class="text-center font-mono font-extrabold">Yeeees!</li>
	</ul>
	<div class="flex justify-center-safe space-x-6 mt-2 shadow-yellow-900">
		<!-- justyfi-end aligns elements at the end, space-x-6 gives space between those elements -->
		<div class="h-16 w-16 rounded-full bg-blue-500">
			<h1 class="text-red-400 shadow-yellow-900">hello mother</h1>
		</div>
		<div class="h-16 w-16 rounded-full bg-red-500"></div>
		<div class="h-16 w-16 rounded-full bg-green-500"></div>
	</div>
	<div class="flex flex-col items-center space-y-6 mt-2 shadow-yellow-900">
		<!-- justyfi-end aligns elements at the end, space-x-6 gives space between those elements -->
		<div class="h-16 w-16 rounded-full bg-blue-500">
			<h1 class="text-red-400 shadow-yellow-900">hello mother</h1>
		</div>
		<div class="h-16 w-16 rounded-full bg-red-500"></div>
		<div class="h-16 w-16 rounded-full bg-green-500"></div>
	</div>


	<div class="grid grid-cols-5 gap-2 mt-2 mx-2 ">
		<div class="h-16 rounded-full bg-blue-500">
			<h1 class="text-red-400 shadow-yellow-900">hello mother</h1>
		</div>
		<div class="h-132 rounded-full bg-red-500"></div>
		<div class="h-16 rounded-full bg-green-500"></div>
	</div>

	<p class="sm:bg-green-500 lg:bg-red-500 md:block hidden">I appear and I'm gay</p>

</template>

<style scoped>
.dark {
	background-color: darkgoldenrod;
}
</style>
