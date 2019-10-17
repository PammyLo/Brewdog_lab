<template lang="html">
  <div>
    <h2>Favourites list</h2>

    <ul>
      <li v-for="(beer, index) in favourites" :key="index">
        {{ beer.name }}</li>
    </ul>

</div>
</template>

<script>
export default {
  name: "favourites-list",
  props: ['favourites']
}
</script>

<style lang="css" scoped>
</style>
