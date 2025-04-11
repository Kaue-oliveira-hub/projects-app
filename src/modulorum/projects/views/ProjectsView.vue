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
      
      <tr v-for="(project, index) in projectStore.projectList" :key="project.id" class="hover:bg-base-300">
        <th>{{ index + 1 }}</th>
        <td>{{ project.nomen }}</td>
        <td>{{ project.chores.length }}</td>
        <progress class="progress progress-secondary w-56" value="10" max="100"></progress>
      </tr>

    </tbody>
  </table>


</div>

<ImputModal 
:aperta="modalAperta" 
@claudere="modalAperta=false"
@valorem="projectStore.addereProject"
placeholder="Nombre del proyecto"
titulus="Nuevo Proyecto"
subtitulus="Escribe el nombre del nuevo proyecto"
/>

<proprium-modal :aperta="propriumModalAperta">


  <template #header>
    <h1 class="text-3xl">Titulo del modal</h1>
  </template>

<template #body>
<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
  Recusandae libero labore deleniti accusamus nobis quas porro! 
  Perspiciatis cumque natus quibusdam numquam. 
  Rem incidunt nobis expedita nam neque doloribus quaerat quos.</p>
</template>

<template #footer>
<div class="flex justify-end">
  <button @click="propriumModalAperta=false" class="btn">Cerrar</button>
  <button @click="propriumModalAperta=false" class="btn btn-primary ml-4">Aceptar</button>
</div>
</template>
</proprium-modal>


<fav-button @click="modalAperta = true">
  <AddCircle />
</fav-button>

<fav-button @click="propriumModalAperta = true" positione="bottom-left">
  <ModalIcon />
</fav-button>

</template>

<script lang="ts" setup>
import AddCircle from '@/modulorum/commune/icons/AddCircle.vue';
import FavButton from '../components/FavButton.vue';
import ImputModal from '@/modulorum/commune/components/ImputModal.vue';
import { ref } from 'vue';
import PropriumModal from '@/modulorum/commune/components/PropriumModal.vue';
import ModalIcon from '@/modulorum/commune/icons/ModalIcon.vue';
import { useProjectsStore } from '../stores/projects.store';


const modalAperta = ref(false);

const propriumModalAperta = ref(false);

const projectStore = useProjectsStore();


</script>