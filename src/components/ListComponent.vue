<template>
  <!-- <li v-on:click="handleClick" >{{country.name}}</li> -->
  <option v-on:click="handleClick">{{country.name}}</option>
</template>

<script>
import { eventBus } from '@/main.js'

export default {
    name: 'list-component',
    props: ['country'],
    methods: {
        handleClick() {
            eventBus.$emit('country-selected', this.country)
        }
    }
}
</script>

<style>

</style>