<template>
<select v-model="country" v-on:change="handleSubmit">
  <option v-for="(country, index) in countries" :country="country" :key="index"  v-bind:value="country" >{{country.name}}</option>
  </select>
</template>

<script>

import{ eventBus } from '../main.js'


export default {
    name: 'list-item',
    props: ['countries'],
            
    methods: {
        handleSubmit: function() {
      eventBus.$emit('country-selected', this.country);
    }
    }
}

</script>

<style  scoped>

</style>