<template>
  <aside class="bg-base-200 w-72 min-h-screen">
    <h2 class="text-lg font-bold mx-4">Projectos</h2>
    <p v-if="projectsStore.nonProject"
    class="text-sm font-bold mx-4">
      No hay proyectos
    </p>

    <ul v-else class="menu bg-base-200 rounded-box w-56">
      <li><a>Item 1</a></li>
      <li>
        <details open>
          <summary>Parent</summary>
          <ul>
            <li><a>Submenu 1</a></li>
            <li><a>Submenu 2</a></li>
            <li>
              <details open>
                <summary>Parent</summary>
                <ul>
                  <li><a>Submenu 1</a></li>
                  <li><a>Submenu 2</a></li>
                </ul>
              </details>
            </li>
          </ul>
        </details>
      </li>
      <li><a>Item 3</a></li>
    </ul>
  </aside>
</template>

<script lang="ts" setup>
import { useProjectsStore } from '../stores/projects.store';

const projectsStore = useProjectsStore();
</script>
