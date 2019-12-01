<template lang="html">
  <div>
  <li v-on:click="handleClick" :value="ship">{{ship.ship_name}}</li>
  </div>
</template>

<script>
import {eventBus} from "../main.js"
export default {
  name: "single-ship",

  props: ["ship"],

  methods: {
    handleClick(){
      eventBus.$emit("ship-selected", this.ship)
},
  }
}
</script>

<style lang="css" scoped>
</style>
