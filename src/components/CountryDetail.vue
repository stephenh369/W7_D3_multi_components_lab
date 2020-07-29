<template>
  <div v-if="country">
      <h3>Country: {{ country.name }}</h3><br>
      <p>Capital: {{ country.capital }}</p>
      <p>Population: {{ country.population }}</p>
      <p>Flag:</p>
      <img :src="country.flag">
  </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>
  img {
    width: 125px;
    height: 100px;
  }
</style>