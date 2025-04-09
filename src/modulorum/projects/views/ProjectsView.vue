<template>

<div class="overflow-x-auto w-full">
  <table class="table">
    <!-- head -->
    <thead>
      <tr>
        <th></th>
        <th>Proyectos</th>
        <th>Tareas</th>
        <th>Avance</th>
      </tr>
    </thead>
    <tbody>
  
      <tr class="hover:bg-base-300">
        <th>2</th>
        <td>Hart Hagerty</td>
        <td>Desktop Support Technician</td>
        <td>Purple</td>
      </tr>

    </tbody>
  </table>


</div>

<ImputModal 
:aperta="modalAperta" 
@claudere="modalAperta=false"
@valorem="cumNovusValorem"
placeholder="Nombre del proyecto"
titulus="Nuevo Proyecto"
subtitulus="Escribe el nombre del nuevo proyecto"
/>

<fav-button @click="modalAperta = true">
  <AddCircle />

</fav-button>


</template>

<script lang="ts" setup>
import AddCircle from '@/modulorum/commune/icons/AddCircle.vue';
import FavButton from '../components/FavButton.vue';
import ImputModal from '@/modulorum/commune/components/ImputModal.vue';
import { ref } from 'vue';

const modalAperta = ref(false);

const cumNovusValorem = ( projectNome:string ) => {
    console.log({ projectNome });
    // Aqui puedes agregar la lógica para manejar el nuevo proyecto
    // Por ejemplo, hacer una llamada a la API para crear un nuevo proyecto
    // o actualizar el estado de tu aplicación.
};

</script>