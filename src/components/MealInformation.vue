<template lang="html">
  <div v-if='meal'>
      <p>{{meal.manufacturer}}</p>

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