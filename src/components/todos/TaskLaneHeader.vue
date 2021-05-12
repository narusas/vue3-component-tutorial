<template>
  <div class="mb-10">
    <h1 class="text-2xl font-bold flex">
      <star-icon
        :class="{ 'text-yellow-300': todoInfo.favorite, 'text-gray-300': !todoInfo.favorite }"
        class="text-3xl h-8 w-8 leading-none align-bottom"
        @click="toggleFavorite"
      />
      <template v-if="isEditing">
        <input v-model="todoInfo.title" @change="changed" ref="titleInput">
      </template>
      <template v-else>
        <div @click="isEditing = true">{{ todoInfo.title }}</div>
      </template>
    </h1>
  </div>
</template>
<script setup>
import { StarIcon } from '@heroicons/vue/solid';
import { toRefs, defineProps, defineEmit , nextTick, ref} from 'vue';
import { onClickOutside } from '@vueuse/core'
const props = defineProps({
  todoInfo: { type: Object },
});
const { todoInfo } = toRefs(props);

const emit = defineEmit(['toggle-favorite']);
console.log('Emit', emit);

const titleInput = ref();
ref: laneHeader = 'Backlogs';
ref: favoriteLane = true;
ref: isEditing = false;
function toggleFavorite() {
  emit('toggle-favorite', todoInfo.value.id);
}

onClickOutside(titleInput, (event) =>{
  changed();
});
function editing() {
  isEditing = true;
  nextTick(()=>{
    titleInput.focus();
  });
}
function changed() {
  console.log("Changed");
  isEditing = false;
}
</script>
