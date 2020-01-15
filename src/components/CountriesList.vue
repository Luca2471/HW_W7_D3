<template lang="html">
  <div>
    <ul>
      <list-item v-for="(country, index) in countries"
      :country="country" :key="index"></list-item>
    </ul>
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


<select id="countries-list" v-model="selectedCountry">
  <list-item disabled value="">Choose a Country :)</list-item>
  <list-item v-for="country in countries" :value="country">{{ country.name }}</list-item>
</select>
