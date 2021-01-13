<template>
  <div>
   <h1>Countries</h1>
   <countries-list> :countries='countries' </countries-list>
  </div>
</template>

<script>

import CountriesList from './components/CountriesList.vue';

export default {
  name: "app",
  data(){
    return {
    countries: []
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(data => this.countries = data);
    console.log(this.countries)
  },
  components: {
    "countries-list": CountriesList
  },
}
</script>

<style>

</style>