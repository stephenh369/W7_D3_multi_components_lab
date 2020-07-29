<template>
  <div v-if="country">
      <h3>Country: {{ country.name }}</h3><br>
      <p>Capital: {{ country.capital }} <br> Population: {{ country.population }}</p>
  </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>

</style>