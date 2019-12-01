<template lang="html">
  <div v-if="ship">
    <h3>Ship Name: {{ship.ship_name}}</h3>
    <p>Ship Type: {{ship.ship_type}}</p>
    <p>Weight KG: {{ship.weight_kg}}</p>
    <p>Home Port: {{ship.home_port}}</p>
    <img :src="ship.image" alt=""    height="300" >

  </div>
</template>

<script>
import {eventBus} from "../main.js"
export default {
  name: "ship-detail",

  props: ['ship']

}
</script>

<style lang="css" scoped>

</style>
