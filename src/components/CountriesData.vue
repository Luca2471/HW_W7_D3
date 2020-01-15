<template lang="html">
  <div v-if="country">
    <h2>{{ cuntry.name }}</h2>
    <h4>{{ country.capital }}</h4>
    <h4>{{ country.population }}</h4>
    <img v-if="selectedCountry" v-bind:src="country.flag">
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name:"country-detail",
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
