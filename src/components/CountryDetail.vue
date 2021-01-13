<template lang='html'>
  <div v-if='country'>
      <h3>Country: {{country.name}}</h3>
      <p>Capital: {{country.capital}}</p>
      <p>Population: {{country.population}}</p>
      <img class="img" :src="country.flag"/>
  </div>
</template>

<script>
export default {
    name: "country-detail",
    props: ['country']
}
</script>

<style scoped>
  .img {
    height: 80px
  }
</style>