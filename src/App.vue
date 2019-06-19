<template>
  <div id="app">

  <detail-country :country='selectedCountry'></detail-country>
  <br>
  <countries-list :countries='countries'></countries-list>

  </div>
</template>

<script>
import CountriesList from './components/CountryList.vue'
import DetailCountry from './components/DetailCountry.vue'
import {eventBus} from './main.js'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(countries => this.countries = countries)
    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country
    })
  },
  components: {
    "countries-list": CountriesList,
    "detail-country": DetailCountry
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
