<script setup lang="ts">
import FabButton from '@/modulorum/commune/components/FabButton.vue';

</script>

<template>

<div class="overflow-x-auto w-full">
  <table class="table">
    <!-- head -->
    <thead>
      <tr>
        <th></th>
        <th>Projectos</th>
        <th>Tareas</th>
        <th>Avance</th>
      </tr>
    </thead>
    <tbody>

      <!-- row 2 -->
      <tr class="hover:bg-base-300">
        <th>1</th>
        <td>Hart Hagerty</td>
        <td>Desktop Support Technician</td>
        <td>Purple</td>
      </tr>

    </tbody>
  </table>

<FabButton @click="() => console.log('clicked')">

  <addCircle />

</FabButton>

</div>

</template>


<script lang="ts" setup>

</script>
