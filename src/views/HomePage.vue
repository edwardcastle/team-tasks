<script setup>
import {ref} from "vue";
import adrain from '@/assets/adrian.jpg'
import alvaro from '@/assets/alvaro.jpg'
import cristian from '@/assets/cristian.jpg'
import david from '@/assets/david.jpg'
import patry from '@/assets/patry.jpg'
import victor from '@/assets/victor.jpg'

const teams = ref([
  {
    logo: adrain,
    task_1: 5,
    task_2: 5,
    task_3: 5,
    task_4: 5,
    task_5: 0
  },
  {
    logo: cristian,
    task_1: 2.5,
    task_2: 3.5,
    task_3: 2,
    task_4: 0,
    task_5: 0
  },
  {
    logo: victor,
    task_1: 1,
    task_2: 2,
    task_3: 2,
    task_4: 0,
    task_5: 0
  },
  {
    logo: patry,
    task_1: 0,
    task_2: 0,
    task_3: 0,
    task_4: 0,
    task_5: 0
  },
  {
    logo: alvaro,
    task_1: 0,
    task_2: 0,
    task_3: 0,
    task_4: 0,
    task_5: 0
  }
])
const sum = (obj) => obj.task_1 + obj.task_2 +obj.task_3 + obj.task_4 + obj.task_5

</script>

<template>
  <v-container class="my-auto" style="min-height: 100vh">
    <h1 class="text-center mt-16">David me tienes quemao</h1>
  <v-table class="mt-16">
    <thead>
    <tr>
      <th class="text-center">
        Logo
      </th>
      <th class="text-center">
        Trabajo con arreglos (js)
      </th>
      <th class="text-center">
        Directivas (v-if, v-else, v-for, v-bind)<br/> vue router
      </th>
      <th class="text-center">
        Fetch <br>(pagina de productos)
      </th>
      <th class="text-center">
        Directivas (v-model) <br> formulario login/register
      </th>
      <th class="text-center">
        Emits
      </th>
      <th class="text-center">
        Puntacion
      </th>
    </tr>
    </thead>
    <tbody>
    <tr
      v-for="team in teams"
      :key="team.name"
    >
      <td class="text-center" style="height: 120px">
        <v-avatar
          size="80"
          class="my-auto"
        >
          <v-img :cover="true" :src="team.logo"></v-img>
        </v-avatar>
      </td>
      <td class="text-center">
        {{ team.task_1 }}
      </td>
      <td class="text-center">
        {{ team.task_2 }}
      </td>
      <td class="text-center">
        {{ team.task_3 }}
      </td>
      <td class="text-center">
        {{ team.task_4 }}
      </td>
      <td class="text-center">
        {{ team.task_5 }}
      </td>
      <td class="text-center">
        {{ sum(team) / 5 }}
      </td>
    </tr>
    </tbody>
  </v-table>
  </v-container>
</template>
