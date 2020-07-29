<template>
  <div>
    <h1>Countries</h1>
    <div class="main-container">
      <!-- <countries-list :countries="countries"></countries-list> -->
      <countries-select :countries="countries"/>
      <country-detail :country="selectedCountry"/>
    </div>
  </div>
</template>

<script>
// import CountriesList from './components/CountriesList.vue';
import CountriesSelect from './components/CountriesSelect.vue';
import CountryDetail from './components/CountryDetail.vue';
import { eventBus } from '@/main.js';

export default {
  name: 'app',
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    // "countries-list" : CountriesList,
    "countries-select" : CountriesSelect,
    "country-detail" : CountryDetail
  }
}
</script>

<style>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>