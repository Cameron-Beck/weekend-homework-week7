<template lang="html">
  <ul>
    <single-ship class="ship-list" v-for="(ship, index) in ships" :ship ="ship" :key ="index">{{ship.ship_name}}</single-ship>
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
.ship-list{
  margin-left: 5px;
  margin-right: 5px;
  margin: 10px;
  list-style-position:inside;
  border: 1px solid black;
}
</style>
