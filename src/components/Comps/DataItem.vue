<template>
    <div class="data-item">
      <span>
        <h1>Artista {{ props.name}}</h1>
      </span>
      <h3>Cancion: {{ props.song}}</h3>
      <h4>Album: {{ props.album}}</h4>
      <p>{{ props.phrase}}</p>
    </div>
  </template>

<script setup lang="ts">
import type { DataList } from '@/interfaces/DataList'
const props = defineProps<DataList>();
</script>


<style scoped>
.data-item {
  border: 1px solid white;
  padding: 10px;
  margin: 5px;
  border-radius: 15px;
  box-shadow: 1px 3px 10px white;
  box-sizing: border-box;
}
</style>