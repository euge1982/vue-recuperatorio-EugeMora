<script setup lang="ts">

//Importaciones
import { ref } from 'vue';
import type { IWeekDay } from '@/models/IWeekDay';
import DayCard from './DayCard.vue';

//Array Reactivo para guardar los dias
const days = ref<IWeekDay[]>([
  { id: 1, name: 'Lunes', selected: false },
  { id: 2, name: 'Martes', selected: false },
  { id: 3, name: 'Miércoles', selected: false },
  { id: 4, name: 'Jueves', selected: false },
  { id: 5, name: 'Viernes', selected: false },
  { id: 6, name: 'Sábado', selected: false },
  { id: 7, name: 'Domingo', selected: false },
])

/**
 * Funcion para seleccionar un dia
 * Cambia el estado de selected a true del dia seleccionado
 * Y a los otros los pone en false
 * @param day - dia a seleccionar
 */
const selectDay = (day: IWeekDay) : void => {
  days.value = days.value.map( d =>
    d.id === day.id ? { ...d, selected: true } : { ...d, selected: false}
  )
}

</script>

<template>
  <div class="p-6 text-center">

    <!--Titulo-->
    <p class="mb-4 text-lg font-medium text-gray-900 ">Seleccione un día:</p>

    <!--Botones-->
    <div class="flex flex-wrap justify-center gap-2 mb-6">
      <button
        v-for="day in days" :key="day.id"
        @click="selectDay(day)"
        class="px-4 py-2 border mt-2 rounded-md bg-fuchsia-200 hover:bg-fuchsia-700 hover:text-white cursor-pointer transition"
      >
        {{ day.name }}
      </button>
    </div>

    <!--Tarjetas-->
    <div class="flex flex-wrap justify-center gap-2 p-8 mt-6">
      <DayCard v-for="day in days" :key="day.id" :day="day"/>
    </div>
  </div>

</template>
