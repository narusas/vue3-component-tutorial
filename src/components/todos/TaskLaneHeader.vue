<template>
  <div class="mb-10 ">
    <h1 class="text-2xl font-bold flex ">
      <star-icon v-if="favoriteLane" class="text-yellow-300 text-3xl h-8 w-8 leading-none align-bottom" />{{ laneHeader }}
    </h1>
  </div>
</template>
<script setup="props">
import { ref } from 'vue';
import { StarIcon } from '@heroicons/vue/solid';
import {useTaskLane} from './todos';
const laneHeader = ref('Backlogs');
const favoriteLane = ref(true);
</script>
