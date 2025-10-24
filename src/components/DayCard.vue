<script setup lang="ts">

//Importacion
import type { IWeekDay } from '../models/IWeekDay';

//Props
const props = defineProps<{
  day: IWeekDay
}>();

/**
 * Funcion que segun el estado de la tarjeta
 * Retorna una clase de Tailwind
 *
 * @param condition - estado de la tarjeta
 * @return - clase de Tailwind
 */
const getState = (condition:boolean): string => {
  if (condition) {
    return 'bg-purple-900 text-white border border-purple-600'
  }
  else {
    return 'bg-gray-200 border border-gray-400 text-gray-900'
  }
}

</script>

<template>
  <div :class="getState(props.day.selected)" class="sm:w-35 lg:w-40 shadow p-4  text-center font-semibold  rounded-lg">
    <h3 class="sm:text-xl lg:text-2xl">{{ props.day.name }}</h3>
  </div>
</template>
