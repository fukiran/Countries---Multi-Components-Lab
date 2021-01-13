<template>
  <div>
    <h1>Countries</h1>
    <div class="main-container">
      <list-item :countries='countries'> </list-item>
      <country-detail :country='selectedCountry'></country-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import ListItem from './components/ListItem';
import CountryDetail from './components/CountryDetail';

export default {
  name: 'app',
  data(){
    return {
    countries: [],
    selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries);

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "country-detail": CountryDetail,
    "list-item": ListItem
  },
}
</script>

<style leng="css">
.main-container {
  display: flex;
  justify-content: space-around;
  }
</style>