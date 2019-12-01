<template lang="html">
  <div v-if="ship">
    <p>Ship Name: {{ship.ship_name}}</p>
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
 p{
   display: flex;
   justify-content: space-between;
   font-size: 20px;
   margin: 10px;
 }
 img{
   height: 300px;
   width: 300px;
   object-fit: cover;
 }
</style>
