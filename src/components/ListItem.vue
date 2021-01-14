<template>
<select class="select"  v-model="selectedCountry" v-on:change="handleSubmit">
  <!-- <option  v-for="(country, index) in countries" :country="country" :key="index"  v-bind:value="country" >{{country.name}}</option> -->
  <option  v-for="country in countries"  :value="country" >{{country.name}}</option>
  </select>
</template>

<script>

import{ eventBus } from '../main.js'


export default {
    name: 'list-item',
    props: ['countries'],
    data() {
        return {
            "selectedCountry": {}
        }
    },
            
    methods: {
        handleSubmit: function() {
      eventBus.$emit('country-selected', this.selectedCountry);
    }
    }
}

</script>

<style  scoped>
.select {
    height: 2em;
}
</style>