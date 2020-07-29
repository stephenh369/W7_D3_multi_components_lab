<template>
  <div>
      <select >
          <list-component v-for="(country, index) in countries" :country="country" :key="index"></list-component>
      </select>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue';
export default {
    name: 'countries-select',
    props: ['countries'],
    components: {
        "list-component": ListComponent
    }
}
</script>

<style>

</style>