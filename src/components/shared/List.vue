<script setup lang="ts">
const props = defineProps({
  title: String,
  data: Array
})
</script>

<template>
  <div class="w-1/3 h-full flex-col shadow-xl rounded-lg">
    <h2 class="text-center font-bold py-2 shadow-sm rounded-lg bg-gray-200">{{ title }}</h2>
    <!-- How to bind map key for typescript ? -->
    <div class="h-8 flex px-4 justify-between items-center my-3" v-for="(item, index) in data" :key:string="item">
      {{ item }}
      <div>
        <slot></slot>
      </div>
    </div>
  </div>
</template>