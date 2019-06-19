<template lang="html">
  <div v-if="country">
    <label><u>Selected Country</u></label>
      <ul>
        <li>Name: {{country.name}}</li>
        <li>Population: {{country.population}}</li>
        <li>Capital: {{country.capital}}</li>
      </ul>
  </div>

</template>

<script>
export default {
  name: 'detail-country',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
