<script setup lang="ts">
import { reactive, watch } from 'vue'
import LayoutPublic from "@/components/layout/LayoutPublic.vue";
import AddTask from '@/components/AddTask.vue'
import TaskList from '@/components/TaskList.vue'

interface DeleteData {
  index: number;
  type: string
}

const tasks = reactive<{ taskData: string[], checkData: string[] }>({
  taskData: [],
  checkData: [],
})

const getUpData = (data: string) => tasks.taskData = [...tasks.taskData, data]

const updateTaskData = (index: number) => {
  tasks.checkData = [...tasks.checkData, tasks.taskData[index]]
  tasks.taskData.splice(index, 1)
}
const updateCheckData = (data: DeleteData) =>
  data.type === 'task' ? tasks.taskData.splice(data.index, 1) : tasks.checkData.splice(data.index, 1)
</script>

<template>
  <LayoutPublic>
    <AddTask @updateData="getUpData" />
    <TaskList :data="tasks" @updateDeleteData="updateCheckData" @updateTaskData="updateTaskData" />
  </LayoutPublic>
</template>
