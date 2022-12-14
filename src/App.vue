<script setup lang="ts">
import { reactive, watch } from 'vue'
import LayoutPublic from "@/components/layout/LayoutPublic.vue";
import AddTask from '@/components/AddTask.vue'
import TaskList from '@/components/TaskList.vue'

const tasks = reactive<{ taskData: string[], checkData: string[] }>({
  taskData: [],
  checkData: [],
})

const getUpData = (data: string) => tasks.taskData = [...tasks.taskData, data]

const updateTaskData = (index: number) => {
  tasks.checkData = [...tasks.checkData, tasks.taskData[index]]
  tasks.taskData.splice(index, 1)
}
const updateCheckData = (index: number) => tasks.checkData.splice(index, 1)
</script>

<template>
  <LayoutPublic>
    <AddTask @updateData="getUpData" />
    <TaskList :data="tasks" @updateDeleteData="updateCheckData" @updateTaskData="updateTaskData" />
  </LayoutPublic>
</template>
