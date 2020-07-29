<template>
  <div>
      <select v-on:change="handleChange" v-model="selectedCountry">
          <option v-for="(country, index) in countries" :country="country" :key="index" v-bind:value="country">{{ country.name }}</option>
      </select>
  </div>
</template>

<script>
import { eventBus } from '@/main.js';
export default {
    name: 'countries-select',
    data() {
        return {
            selectedCountry: null
        }
    },
    props: ['countries'],
    methods: {
        handleChange() {
            eventBus.$emit('country-selected', this.selectedCountry)
        }
    }
}
</script>

<style>

</style>