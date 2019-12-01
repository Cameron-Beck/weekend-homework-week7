<template lang="html">
  <ul>
    <single-ship v-for="(ship, index) in ships" :ship ="ship" :key ="index">{{ship.ship_name}}</single-ship>
  </ul>
</template>

<script>
import SingleShip from "./SingleShip.vue";
export default {
  name: "ship-list",

  props: ["ships"],

  components:{
    "single-ship": SingleShip
  }
}
</script>

<style lang="css" scoped>
</style>
