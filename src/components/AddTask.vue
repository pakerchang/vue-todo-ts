<script setup lang="ts">
import LayoutAddTask from './layout/LayoutAddTask.vue';
import { PlusIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <LayoutAddTask>
    <input class="w-full rounded-lg px-3 py-2 focus:outline-none" type="text" placeholder="Add a new task" />
    <button class="w-6 h-6 mr-3 hover:rounded-lg hover:bg-gray-100" type="submit">
      <PlusIcon class="w-6 h-6" />
    </button>
  </LayoutAddTask>
</template>