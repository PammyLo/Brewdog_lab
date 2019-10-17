<template lang="html">
<div>
  <h2>Beer list</h2>
  <ul>
    <beer-list-item v-for="(beer, index) in beers" :beer="beer" :key="index" >
      {{ beer.name }} </beer-list-item>
  </ul>
</div>
</template>

<script>
import BeerListItem from '@/components/BeerListItem.vue';

export default {
  name: "beer-list",
  props: ['beers'],
  components: {
  "beer-list-item": BeerListItem
  }
}
</script>

<style lang="css" scoped>
flex-basis: 30%;
</style>
