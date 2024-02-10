<template>
    <div class="data">
      <ul class="data-list">
        <DataItem v-bind="component" v-for="(component, index) in ComponentData" :key="index" />
      </ul>
    </div>
  </template>
<script setup lang="ts">
import ComponentData from '@/data/ComponetData';
import DataItem from '@/components/Comps/DataItem.vue'
</script>

<style scoped>
 .data {
  display: flex;
  justify-content: center;
  
}

.data-list {
  display: grid;
  grid-template-columns: repeat(2, 1fr); 
  gap: 20px; 
}
</style>