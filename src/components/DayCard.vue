<script setup lang="ts">

import type { IWeekDay } from '../models/IWeekDay';

const props = defineProps<{
  day: IWeekDay
}>();

const getState = (condition:boolean): string => {
  if (condition) {
    return 'bg-gray-50 border'
  }
  else {
    return 'bg-blue-500 text-white'
  }
}

</script>

<template>
  <div :class="getState(props.day.selected)" class="w-32 p-4 m-4">
    <h3 class="text-2xl">{{ props.day.name }}</h3>
  </div>
</template>
