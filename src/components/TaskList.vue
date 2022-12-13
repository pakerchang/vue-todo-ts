<script setup lang="ts">
import LayoutList from "@/components/layout/LayoutList.vue";
import List from "@/components/shared/List.vue"
import { CheckIcon, TrashIcon } from '@heroicons/vue/24/outline'
</script>
<template>
  <LayoutList>
    <List title="Task List">
      <button class="rounded-lg border shadow-md mr-4">
        <CheckIcon class="w-5 h-5" />
      </button>
      <button class="rounded-lg border shadow-md ">
        <TrashIcon class="w-5 h-5" />
      </button>
    </List>
    <List title="Done">
      <button class="rounded-lg border shadow-md ">
        <TrashIcon class="w-5 h-5" />
      </button>
    </List>
  </LayoutList>
</template>