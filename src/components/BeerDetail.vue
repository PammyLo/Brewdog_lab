<template lang="html">
  <div>
    <h2>Beer details</h2>
    <h3>{{ beer.name }}</h3>
    <p>{{ beer.tagline }}</p>
    <p>{{ beer.description }}</p>
    <p>Food pairing:<br>{{ beer.food_pairing }}</p>
    <button v-on:click="handleClick">Add to favourites</button>
  </div>
</template>

<script>
import {eventBus} from '@/main.js';

export default {
  name: "beer-detail",
  props: ['beer'],
  methods: {
    handleClick(){
      eventBus.$emit('fav-selected', this.beer);
    }
  }
}
</script>

<style lang="css" scoped>
div {
  flex-basis: 30%;
}
</style>
