<template>
  <div>
    <h1>Food Reviews</h1>
    <div class="main-container">
      <meals-list :meals='meals'></meals-list>
    </div>
  </div>
</template>s

<script>
import { eventBus } from './main.js';
import MealsList from './components/MealsList.vue';
import MealInformation from './components/MealInformation.vue'

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
  .then(product => this.meals = product)

  eventBus.$on('meal-selected', (meal) => {
    this.selectedMeal = meal
  })
},
components: {
  "meals-list": MealsList,
  "meal-information": MealInformation

}

}
</script>

<style>
  .main-container {
    display: flex;
  }
</style>