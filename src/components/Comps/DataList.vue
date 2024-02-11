<template>
    <button @click="showmodal = true">Agregar</button>
    <transition>
        <div class="modal-content" v-if="showmodal">
      <h2>Agregar Nuevo Artista</h2>
      <form>
        <label>Artista:</label>
        <input v-model="name" required />

        <label>Canción:</label>
        <input v-model="song" required />

        <label>Álbum:</label>
        <input v-model="album" required />

        <label>Frase:</label>
        <textarea v-model="phrase" required></textarea>

        <div class="modal-buttons">
          <button @click="saveData">Guardar</button>
          <button @click="closeModal">Cancelar</button>
        </div>
      </form>
    </div>
        </transition>
    <div class="data">
      <ul class="data-list">
        <DataItem v-bind="component" v-for="(component, index) in ComponentData" :key="index" />
      </ul>
    </div>
  </template>
  
  <script setup lang="ts">
  import ComponentData from '@/data/ComponetData';
  import DataItem from '@/components/Comps/DataItem.vue'
  import { ref } from 'vue';

const showmodal = ref(false);
const name = ref('');
const song = ref('');
const album = ref('');
const phrase = ref('');

const openModal = () => {
  showmodal.value = true;
};

const closeModal = () => {
  showmodal.value = false;
};


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
    margin: 20px; 
  }
  

  .data-list .data-item {
    margin: 10px;
  }

  .modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 999;
  }
  
  .modal-content {
    background: white;
    color: black;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  }
  
  form {
    display: grid;
    gap: 10px;
  }
  
  .modal-buttons {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
  }
  
  button {
    padding: 10px;
    cursor: pointer;
    border: 1px solid #333;
    background-color: #eee;
  }
  </style>
  