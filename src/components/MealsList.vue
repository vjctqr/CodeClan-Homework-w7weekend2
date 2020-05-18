<template>
  <div>
    <ul>
      <the-list-component v-for="(toShowList, index) in meals" :toShowList="showList" :key="index"></the-list-component>
    </ul>
  </div>
</template>

<script>
import TheListComponent from './TheListComponent.vue';

export default {
    name: 'meals-list',
    props: ['meals'], 
    components:{
        "the-list-component": TheListComponent
    }
}
</script>

<style>

</style>