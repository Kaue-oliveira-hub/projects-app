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

<fav-button @click="() => console.log('clicked')">
  <AddCircle />

</fav-button>


</template>

<script lang="ts" setup>
import AddCircle from '@/modulorum/commune/icons/AddCircle.vue';
import FavButton from '../components/FavButton.vue';


</script>