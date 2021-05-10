<template>
  <div class="w-full mx-auto rounded-lg border border-gray-700 p-8 lg:py-12 lg:px-14 text-gray-300" style="max-width: 400px">
    <task-lane-header v-bind:todo-info="todoInfo" />

    <task-list />
    <task-add-control />
  </div>
</template>

<script setup>
import { defineProps, onMounted, ref } from 'vue';
import axios from 'axios';

import TaskLaneHeader from './TaskLaneHeader.vue';
import TaskList from './TaskList.vue';
import TaskAddControl from './TaskAddControl.vue';

const props = defineProps({
  todoInfo: Object,
});

const todos = ref([]);

onMounted(async () => {
  todos.value = await axios.get(`/${props.todoInfo.info}.json`);
});
</script>

<style scoped></style>
