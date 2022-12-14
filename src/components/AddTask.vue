<script setup lang="ts">
import { ref, } from 'vue'
import LayoutAddTask from './layout/LayoutAddTask.vue';
import { PlusIcon } from '@heroicons/vue/24/outline'

const inputQuery = ref<string>('')
const emit = defineEmits(['updateData'])

const handleUpdate = (): void => {
  emit("updateData", inputQuery.value)
  inputQuery.value = ""
}
</script>

<template>
  <LayoutAddTask>
    <input class="w-full rounded-lg px-3 py-2 focus:outline-none" type="text" placeholder="Add a new task"
      @change="(e: Event) => { inputQuery = (e.target as HTMLInputElement).value }" @keyup.enter="handleUpdate"
      :value="inputQuery" />
    <button class=" w-6 h-6 mr-3 hover:rounded-lg hover:bg-gray-100" @click="handleUpdate">
      <PlusIcon class="w-6 h-6" />
    </button>
  </LayoutAddTask>
</template>