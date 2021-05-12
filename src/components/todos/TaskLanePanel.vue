<template>
  <div class="w-full mx-auto rounded-lg border border-gray-700 p-8 lg:py-12 lg:px-14 text-gray-300" style="max-width: 400px">
    <task-lane-header v-bind:todo-info="todoInfo" @toggle-favorite="toggleFavorite" />

    <task-list :todos="todos" />
    <task-add-control />
  </div>
</template>

<script setup>
import { defineProps, onMounted, ref, toRefs } from 'vue';
import axios from 'axios';

import TaskLaneHeader from './TaskLaneHeader.vue';
import TaskList from './TaskList.vue';
import TaskAddControl from './TaskAddControl.vue';

const props = defineProps({
  todoInfo: Object,
});

const { todoInfo } = toRefs(props);

const tasks = ref({});
const taskList = ref([]);
onMounted(async () => {
  const res = await axios.get(`/${todoInfo.value.id}.json`);
  console.log("res", res);
  tasks.value = res.data.tasks;
  taskList.value = res.data.taskList;
});

function toggleFavorite(todosId) {
  todoInfo.value.favorite = !todoInfo.value.favorite;
}
</script>

<style scoped></style>
