<script setup lang="ts">

import { ref } from 'vue';
import type { IWeekDay } from '../models/IWeekDay';
import DayCard from './DayCard.vue';

const days = ref<IWeekDay[]>([
  { id: 1, name: 'Lunes', selected: false },
  { id: 2, name: 'Martes', selected: false },
  { id: 3, name: 'Miércoles', selected: false },
  { id: 4, name: 'Jueves', selected: false },
  { id: 5, name: 'Viernes', selected: false },
  { id: 6, name: 'Sábado', selected: false },
  { id: 7, name: 'Domingo', selected: false },
])

const selectDay = (day: IWeekDay) : void => {
  days.value = days.value.map( d =>
    d.id === day.id ? { ...d, selected: true } : { ...d, selected: false}
  )
}

</script>

<template>
  <div v-for="day in days" :key="day.id">
    <button @click="selectDay(day)">{{ day.name }}</button>

  </div>
  <div class="flex  flex-wrap sm:flex-col lg:flex-row ">
    <DayCard v-for="day in days" :key="day.id" :day="day"/>
  </div>
</template>
