<template lang="html">
  <div>
    <p>{{meal.name}}</p>
    <button v-on:click="displayInfo"></button>
  </div>  
</template>

<script>
import {eventBus} from '../main.js'

export default {
    name: 'the-list-component',
    props: ['meal'],
    methods: {
        displayInfo: function(){
            eventBus.$emit('meal-selected', this.meal)
        },
    },
 

}
</script>

<style>

</style>