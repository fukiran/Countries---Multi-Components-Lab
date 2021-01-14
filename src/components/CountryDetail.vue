<template>
  <div v-if='country'>
      <h3>Country: {{country.name}}</h3>
      <p>Population: {{country.population}}</p>
      <p>Capital: {{country.capital}}</p>
      
      <img class="img" :src="country.flag"/>
      <p>Languages:</p>
      
      <ul v-for="(language, index) in country.languages" :key="index">
        <li>»{{language.name}}«  
          Native Name: {{language.nativeName}}</li>
        
      </ul>
      
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
  li {
    list-style-type: none;
  }
</style>