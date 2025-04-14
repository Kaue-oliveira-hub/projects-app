<template>
  <BreadCrumbs :nomen="project?.nomen ??'No name'"/>
</template>

<script setup lang="ts">
import BreadCrumbs from '@/modulorum/commune/components/BreadCrumbs.vue';
import { useProjectsStore } from '../stores/projects.store';
import { ref, watch } from 'vue';
import { Project } from '

interface Props{
    id:string;
}
const props = defineProps<Props>();

const projectStore = useProjectsStore();

const project = ref<Project>();

watch (() => props.id,()=>{
   project = projectStore.projectList.find(project => project.id === props.id )
},
{

    immediate: true,
    
})



</script>
