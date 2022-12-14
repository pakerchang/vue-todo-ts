<script setup lang="ts">
import { ref } from 'vue'
import LayoutList from "@/components/layout/LayoutList.vue";
import List from "@/components/shared/List.vue"
import { CheckIcon, TrashIcon } from '@heroicons/vue/24/outline'

const props = defineProps<{ data: any }>()
const emits = defineEmits(['updateDeleteData', 'updateTaskData'])
const taskIndex = ref<number>(0)

const getItemIndex = (data: number) => taskIndex.value = data

const handleTaskCheck = (): void => emits('updateTaskData', taskIndex.value)
const handleTaskDelete = (): void => emits("updateDeleteData", taskIndex.value)

</script>
<template>
  <LayoutList>
    <List title="Task List" :data="data.taskData" @update="getItemIndex">
      <button class="rounded-lg border shadow-md mr-4" @click="handleTaskCheck">
        <CheckIcon class="w-5 h-5" />
      </button>
      <button class="rounded-lg border shadow-md" @click="handleTaskDelete">
        <TrashIcon class="w-5 h-5" />
      </button>
    </List>
    <List title="Done" :data="data.checkData" @update="getItemIndex">
      <button class="rounded-lg border shadow-md" @click="handleTaskDelete">
        <TrashIcon class="w-5 h-5" />
      </button>
    </List>
  </LayoutList>
</template>