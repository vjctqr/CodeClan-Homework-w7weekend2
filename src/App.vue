<template>
  <div>
    <h1>Food Reviews</h1>
    <the-list-component :meals="meals"></the-list-component>
    <meal-information :toShowList='selectedMeal'></meal-information>
  </div>
</template>

<script>
import {eventBus} from './main.js';
import MealsList from './components/MealsList.vue';
import MealInformation from './components/MealInformation.vue'

export default {
  name: 'app',
  components: {
    "meal-information": MealInformation,
     "meals-list": MealsList
  },
  data(){
    return {
      meals: [],
      selectedMeal: null
    };
  },
  methods: {
    getMeals: function() {
      const promises = [1, 2, 3, 4, 5].map(num => {
        return fetch(
          'https://thereportoftheweek-api.herokuapp.com/reports?category=Running%20On%20Empty'
        ).then(res => res.json());
      });
      Promise.all(promises)
        .then(data => {
          const mealData = data.reduce(
            (flat, toFlatten) => flat.concat(toFlatten),
            []
          );
        })
  
      },
      
  },
  mounted(){
    this.getMeals();

    eventBus.$on('meal-selected', meal => (this.selectedMeal = meal));
  }
}

</script>

<style>
 
</style>