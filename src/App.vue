<template lang="html">
  <div>
    <h1>Brewdog Beers</h1>

    <div class='main-container'>
      <beer-list :beers='beers'></beer-list>
      <beer-detail v-if='selectedBeer' :beer='selectedBeer'></beer-detail>
      <favourites-list v-if='favourites.length' :favourites='favourites'></favourites-list>
    </div>

  </div>
</template>

<script>
import BeerList from '@/components/BeerList.vue';
import BeerDetail from '@/components/BeerDetail';
import FavList from '@/components/FavList.vue';
import {eventBus} from '@/main.js';

export default {
  name: "app",
  data (){
    return {
      beers: [],
      selectedBeer: null,
      favourites: []
    }
  },
  mounted () {
    fetch('https://api.punkapi.com/v2/beers')
    .then(result => result.json())
    .then(data => this.beers = data);

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer;
    });
    eventBus.$on('fav-selected', (beer) => {
      if (!this.favourites.includes(beer)) {this.favourites.push(beer)};
    });
    eventBus.$on('fav-to-remove', (beerToRemove) => {
      this.favourites = this.favourites.filter(beer => beer.name !== beerToRemove.name);
    });
  },
  components: {
    "beer-list": BeerList,
    "beer-detail": BeerDetail,
    "favourites-list": FavList
  }
}
</script>

<style lang="css" scoped>
.main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
