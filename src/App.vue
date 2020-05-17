<template>
  <div>
    <h1>Food Reviews</h1>
    <div>
      <meals-list :meals='meals'></meals-list>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import MealsList from './components/MealsList.vue'

export default {
  name: 'app',
  data(){
    return {
      meals: [],
      selectedMeal: null
    };
  },
mounted(){
  fetch('https://thereportoftheweek-api.herokuapp.com/reports?category=Running%20On%20Empty')
  .then(res => res.json())
  .then(meals => this.meals = meals)

},
}
</script>

<style>

</style>