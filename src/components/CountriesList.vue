<template lang="html">
  <div>
    <select v-on:change="handleSelect" v-model="selectedCountry">
      <option disabled value="">Choose a Country :)</option>
      <option v-for="country in countries" :value="country">{{ country.name }}</option>
    </select>
  </div>
</template>

<script>
import ListItem from './ListItem.vue';

export default {
  name: 'countries-list',
  props: ['countries'],
  components:{
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>



<!-- <ul>
  <list-item v-for="(country, index) in countries"
  :country="country" :key="index"></list-item>
</ul>

  <select id="countries-list" v-model="selectedCountry">
    <option disabled value="">Choose a Country :)</option>
    <option v-for="country in countries" :value="country">{{ country.name }}</option>
  </select> -->
