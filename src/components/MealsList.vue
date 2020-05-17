<template lang="html">
  <div>
      <ul>
        <the-list-component v-for="(meal, index) in meals" :meals="meal" :key="index"></the-list-component>
      </ul>
  </div>
</template>

<script>
import TheListComponent from './TheListComponent.vue'

export default {
    name: 'meals-list',
    props: ['meals'],
    components:{
        "the-list-component": TheListComponent
    }

}
</script>

<style lang="css" scoped>

</style>