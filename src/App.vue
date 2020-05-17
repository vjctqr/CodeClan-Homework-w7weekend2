<template>
  <div>
    <h1>Food Reviews</h1>
  </div>
</template>

<script>
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