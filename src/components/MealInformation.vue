<template lang="html">
  <div v-if='meal'>
      <h3>{{meal.manufacturer}}</h3>

  </div>
  
</template>

<script>
import {eventBus} from '../main.js';

export default {
    name: 'meal-information',
    props: ['meal']


}
</script>

<style>

</style>