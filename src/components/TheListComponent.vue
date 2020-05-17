<template lang="html">

  
</template>

<script>
import {eventBus} from '../main.js'

export default {
    name: 'the-list-component',
    props: ['meal'],
    methods: {
        handleClick(){
            eventBus.$emit('meal-selected', this.meal)
        }
    }

}
</script>

<style>

</style>