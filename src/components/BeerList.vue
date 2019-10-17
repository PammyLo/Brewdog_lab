<template lang="html">
<div>
  <h1>beer list</h1>
  <ul>
    <li v-for="(beer, index) in beers" :key="index" > {{ beer.name }} </li>
  </ul>
</div>
</template>

<script>
export default {
  name: "beer-list",
  props: ['beers']
}
</script>

<style lang="css" scoped>
</style>
