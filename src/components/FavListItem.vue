<template lang="html">
  <li v-on:click="handleClick"> {{beer.name}}</li>
</template>

<script>
import {eventBus} from '@/main.js';

export default {
  name: "fav-list-item",
  props: ['beer'],
  methods: {
    handleClick(){
      eventBus.$emit('fav-to-remove', this.beer);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
