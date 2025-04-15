<template>

  <div class="w-full">
<section class="m-2">
  <BreadCrumbs :nomen="project?.nomen ?? 'No name'" />
</section>


<section class="m-2">

  <div class="overflow-x-auto">
  <table class="table">
    <!-- head -->
    <thead>
      <tr>
        <th></th>
        <th>Tarea</th>
        <th>Completada</th>
      </tr>
    </thead>
    <tbody>


      <tr v-for="(chore, index) in project?.chores" :key="chore.id">
  <th>{{ index + 1 }}</th>
  <td>{{ chore.nomen }}</td>
  <td>{{ chore.date }}</td>
</tr>


      <tr class="hover:bg-base-300">
        <th></th>
        <td>
          <input type="text"
          class="input input-primary w-full opacity-60 transition-all hover:opacity-100 focus:opacity-100"
          placeholder="Nueva tarea"
          v-model="novusChore"
          @keyup.enter="addereChore"
          >
        </td>
      </tr>



    </tbody>
  </table>
</div>

</section>
</div>

</template>

<script setup lang="ts">
import BreadCrumbs from '@/modulorum/commune/components/BreadCrumbs.vue';
import { useProjectsStore } from '../stores/projects.store';
import type { Project } from '../interfaces/projects.interface';
import { useRouter } from 'vue-router';
import { ref, watch } from 'vue';




interface Props{
  id: string;
}

const router = useRouter();
const props = defineProps<Props>();
const projectStore = useProjectsStore();
const project = ref<Project | null>()
const novusChore = ref();
const addereChore = () => {
  if (!project.value) return;
  projectStore.addereChoreAdProject(project.value.id, novusChore.value);
  novusChore.value = "";
}

watch( () => props.id, ( ) => {
  project.value = projectStore.projectList.find(project => project.id === props.id);
  if (!project.value){
    router.replace('/')
  }
},

{
  immediate: true
});





</script>


