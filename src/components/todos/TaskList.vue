<template>
  <div class="mb-10">
    <ul class="-mx-1">
      <li
        class="px-2 py-2 rounded transition-all flex text-md"
        :class="{
          'bg-gray-700 shadow-lg px-4 py-4 my-10 -mx-2': false,
          'mb-1 cursor-pointer': true,
        }"
      >
        <div class="flex-none w-10 leading-none">
          <input type="checkbox" />
        </div>
        <div class="flex-grow max-w-full">
          
          <div class="w-full leading-none">
            <h3 class="text-md leading-none truncate w-full pr-10 text-gray-300">New todo...</h3>
            <input
              type="text"
              class="text-md w-full bg-transparent text-gray-300 leading-none focus:outline-none mb-2"
              placeholder="New todo..."
            />
          </div>

          <div class="w-full flex justify-end">
            <button class="p-1 -mr-1 focus:outline-none hover:text-red-300">
              <i class="mdi mdi-trash-can-outline"></i>
            </button>
          </div>
        </div>
      </li>
      <li
        class="px-2 py-2 rounded transition-all flex text-md"
        :class="{
          'bg-gray-700 shadow-lg px-4 py-4 my-10 -mx-2': false,
          'mb-1 cursor-pointer': true,
        }"
      >
        <div class="flex-none w-10 leading-none">
          <input type="checkbox" />
        </div>
        <div class="flex-grow max-w-full">
          
          <div class="w-full leading-none">
            <h3 class="text-md leading-none truncate w-full pr-10 text-gray-300">New todo...</h3>
           
          </div>

          <div class="w-full flex justify-end">
            <button class="p-1 -mr-1 focus:outline-none hover:text-red-300">
              <i class="mdi mdi-trash-can-outline"></i>
            </button>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script setup></script>
