<template>
  <div>
    <h1>Countrys in Planet Earth</h1>
    <div class="main-container">
      <countries-list :countries='countries'></countries-list>
      <country-data :country="selectedCountry"></country-data>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import CountriesData from './components/CountriesData.vue';
import { eventBus } from './main.js';

export default {
  name: 'app',
  data(){
    return{
      countries: [],
      selectedCountry: null
    };

  },
  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
      .then(res => res.json())
      .then(countries => this.countries = countries )

      eventBus.$on('country-selected', (country) => {
        this.selectedCountry = country
      })
  },
  components: {
    "countries-list": CountriesList,
    "countries-data": CountriesData
  }
}
</script>

<style>
</style>
