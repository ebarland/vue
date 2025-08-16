<script setup>
import { ref, onMounted } from "vue";

const name = ref('nissen');
const status = ref('inactive');
const tasks = ref(['task 1', 'task 2', 'task 3']);
const link = 'https://youtu.be/VeNfHj6MhgA?t=2924';
const newTask = ref('');

const ToggleStatus = () => {
	if (status.value === 'active') {
		status.value = 'inactive'
	}
	else if (status.value === 'inactive') {
		status.value = 'pending'
	}
	else {
		status.value = 'active'
	}
};

const AddTask = () => {
	if (newTask.value.trim() !== '') {
		tasks.value.push(newTask.value);
		newTask.value = '';
	}
};

const DeleteTask = (index) => {
	tasks.value.splice(index, 1);
};

const ChangeTaskState = (index) => {
	let task = tasks.value.at(index);
	if (task === 'active')
		tasks.value[index] = 'paused';
	else if (task === 'paused')
		tasks.value[index] = 'active';
	else
		console.log('Cannot pause a task that is not active!');
};

onMounted(async () => {
	try {
		const res = await fetch("https://jsonplaceholder.typicode.com/todos");
		const data = await res.json();
		tasks.value = data.map((task) => task.title);
	}
	catch (error) {
		console.log(error);
	}
});

</script>

<template>
	<h1>You did it, {{ name }}!</h1>
	<p v-if="status === 'active'">{{ name }} is active!</p>
	<p v-else-if="status === 'pending'">{{ name }} is pending!</p>
	<p v-else>{{ name }} is inactive!</p>
	<p v-for="item in items">{{ item }}</p>

	<!-- .prevent is to avoid having to do event.prevent in JS -->
	<form @submit.prevent="AddTask">
		<label for="newTask">Add Task!</label>
		<input type="text" id="newTask" name="newTask" v-model="newTask"></input>
		<button type="submit">Submit!</button>
	</form>

	<h3>Tasks:</h3>
	<ul>
		<li v-for="(task, index) in tasks" :key="task">
			<span>
				{{ task }}
			</span>
			<button @click="DeleteTask(index)">Delete!</button>
			<button @click="ChangeTaskState(index)">Pause!</button>
		</li>
	</ul>

	<!-- <a v-bind:href="link">Google-time!!!</a> -->
	<a :href="link" target="_blank">Fortsett video</a>
	<br />

	<!-- <button v-on:click="ToggleStatus">change status</button> -->
	<button @click="ToggleStatus">change status</button>
</template>

<style scoped></style>
