<script setup lang="ts">
import LayoutPublic from "@/components/layout/LayoutPublic.vue";
import AddTask from '@/components/AddTask.vue'
import TaskList from '@/components/TaskList.vue'

</script>

<template>
  <LayoutPublic>
    <AddTask />
    <TaskList />
  </LayoutPublic>
</template>
