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

const cumNovusValorem = ( projectNome:string ) => {
    console.log({ projectNome });
    // Aqui puedes agregar la lógica para manejar el nuevo proyecto
    // Por ejemplo, hacer una llamada a la API para crear un nuevo proyecto
    // o actualizar el estado de tu aplicación.
};

</script>