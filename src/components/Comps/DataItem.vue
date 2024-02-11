<template>
    <div class="data-item" :style="{ color: textColor, backgroundColor: bgColor }">
      <div class="content">
        <h1 class="artist">{{ props.name }}</h1>
        <h4>Cancion:</h4>
        <h3>{{ props.song }}</h3>
        <h4>Album;</h4>
        <h4>{{ props.album }}</h4>
        <h4>Frase:</h4>
        <p>{{ props.phrase }}</p>
        <div class="buttons">
          <button @click="color">Color texto</button>
          <button @click="backgroudcolor">Color de fodo</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup lang="ts">
  import type { DataList } from '@/interfaces/DataList';
  import { ref } from 'vue';
  
  const props = defineProps<DataList>();
  const colors = ['red', 'yellow', 'black', 'white'];
  const bckcol = ['black', 'white', '#B5B2B2'];
  let textColorts = 5;
  let bgColorts = 4;
  
  const color = () => {
    textColorts = (textColorts + 1) % colors.length;
    textColor.value = colors[textColorts];
  };
  
  const backgroudcolor = () => {
    bgColorts = (bgColorts + 1) % colors.length;
    bgColor.value = bckcol[bgColorts];
  };
  
  const textColor = ref(colors[textColorts]);
  const bgColor = ref(bckcol[bgColorts]);
  </script>
  
  <style scoped>
  .data-item {
    border: 1px solid white;
    padding: 20px;
    margin: 20px;
    border-radius: 15px;
    box-shadow: 1px 3px 10px white;
    box-sizing: border-box;
    text-align: center;
  }
  
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .artist {
    font-size: 1.5em;
    margin-bottom: 10px;
  }
  
  .buttons {
    margin-top: 10px;
    padding: 10%;
  }
  
  button {
  margin-top: 10px;
  padding: 5px 10px;
  cursor: pointer;
  border: 1px solid white;
  border-radius: 5px;
  box-shadow: 1px 3px 10px white;
}
  
    p {
        text-align: justify;
    }
  </style>
  
  