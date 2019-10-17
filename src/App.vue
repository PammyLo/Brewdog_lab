<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>
    <beer-list :beers='beers'></beer-list>
  </div>
</template>

<script>
import BeerList from '@/components/BeerList.vue';

export default {
  name: "app",
  data (){
    return {
      beers: [],
      selectedBeer: null
    }
  },
  mounted () {
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(data => this.beers = data);
  },
  components: {
    "beer-list": BeerList
  }
}
</script>

<style lang="css" scoped>
</style>
