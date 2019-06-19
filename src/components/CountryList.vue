<template lang="html">
  <div class="">
    
  <country-list-item v-for="(country, index) in countries" :country="country" :key="index"></country-list-item>


  </div>
</template>

<script>
import CountryListItem from './CountryListItem.vue'

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "country-list-item": CountryListItem
  }
}
</script>

<style lang="css" scoped>
</style>
