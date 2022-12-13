<script setup lang="ts">
import LayoutAddTask from './layout/LayoutAddTask.vue';
import { PlusIcon } from '@heroicons/vue/24/outline'
</script>

<template>
  <LayoutAddTask>
    <h1>Add Task</h1>
    <div class="">
      <input class="rounded-lg px-3 py-2 focus:outline-none" type="text" placeholder="Add a new task" />
      <button class="pr-3 w-6 h-6" type="submit">
        <PlusIcon class="w-6 h-6" />
      </button>
    </div>

  </LayoutAddTask>
</template>