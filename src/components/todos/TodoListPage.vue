<template>
  <div class="min-w-screen min-h-screen bg-gray-800 flex items-center justify-center px-5 py-5 text-left">
    <task-lane-panel v-for="todoInfo in todoInfos" v-bind:key="todoInfo.id" v-bind:todoInfo="todoInfo" />
  </div>
</template>
<script setup>
import { onMounted, ref } from 'vue';
import TaskLanePanel from './TaskLanePanel.vue';
import axios from 'axios';

const todoInfos = ref([]);
onMounted(async () => {
  const response = await axios.get('/todos.json');
  console.log(response);
  todoInfos.value = response.data;
});
</script>
