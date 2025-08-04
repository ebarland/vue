<script>
export default
	{
		data() {
			return {
				name: 'nissen',
				status: 'pending',
				tasks: ['task 1', 'task 2', 'task 3'],
				link: 'https://google.com'
			};
		},
		methods: {
			ToggleStatus() {
				if (this.status === 'active') {
					this.status = 'inactive'
				}
				else if (this.status === 'inactive') {
					this.status = 'pending'
				}
				else {
					this.status = 'active'
				}
			}
		}
	}
</script>

<template>
	<h1>You did it, {{ name }}!</h1>
	<p v-if="status === 'active'">{{ name }} is active!</p>
	<p v-else-if="status === 'pending'">{{ name }} is pending!</p>
	<p v-else>{{ name }} is inactive!</p>

	<h3>Tasks:</h3>
	<ul>
		<li v-for="task in tasks" :key="task">{{ task }}</li>
	</ul>
	<!-- <a v-bind:href="link">Google-time!!!</a> -->
	<a :href="link">Google-time!!!</a>
	<br />
	<!-- <button v-on:click="ToggleStatus">change status</button> -->
	<button @click="ToggleStatus">change status</button>
</template>

<style scoped></style>
