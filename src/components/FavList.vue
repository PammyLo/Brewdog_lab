<template lang="html">
  <div>
    <h2>Favourites list</h2>
    <ul>
      <fav-list-item v-for="(beer, index) in favourites" :beer="beer" :key="index" >
        {{ beer.name }}</fav-list-item>
    </ul>
</div>
</template>

<script>
import {eventBus} from '@/main.js';
import FavListItem from '@/components/FavListItem.vue';

export default {
  name: "favourites-list",
  props: ['favourites'],
  components: {
    "fav-list-item": FavListItem
  }
}
</script>

<style lang="css" scoped>
</style>
