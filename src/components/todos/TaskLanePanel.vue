<template>
  <div class="w-full mx-auto rounded-lg border border-gray-700 p-8 lg:py-12 lg:px-14 text-gray-300" style="max-width: 400px">
    <task-lane-header />
    <task-list />
    <task-add-control />
  </div>
</template>

<script setup>
import TaskLaneHeader from './TaskLaneHeader.vue';
import TaskList from './TaskList.vue';
import TaskAddControl from './TaskAddControl.vue';
</script>

<style scoped>
</style>
