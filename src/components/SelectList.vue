<template lang="html">
  <ul>
    <li v-on:click="handleClick" :value="list">ships</li>
    <li>launches</li>
  </ul>
</template>

<script>
import {eventBus} from "../main.js"
import ShipList from "./ShipList.vue";
export default {
  name: "select-list",
  props: ["list"],

  components:{
    "ship-list": ShipList
  },
  methods: {
      handleClick(){
        eventBus.$emit("list-selected", this.list)
  },
    }

}
</script>

<style lang="css" scoped>
</style>
