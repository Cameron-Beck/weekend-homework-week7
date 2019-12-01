<template lang="html">
  <div class="container1">
    <select-list>Ship List</select-list>
    <ship-list class="ship-list"  :ships = "ships">  </ship-list>
    <ship-detail class="container2" :ship = "selectedShip"> </ship-detail>
  </div>
</template>

<script>
import ShipDetail from "./components/ShipDetail.vue"
import ShipList from "./components/ShipList.vue"
import SingleShip from "./components/SingleShip.vue"
import SelectList from "./components/SelectList.vue"

import {eventBus} from "./main.js"
export default {
  name: "App",
  data(){
    return {
      ships: [],
      selectedShip: null,
      selectedList: null,
      favorites: [],
      beerToRemove: ""
    }
  },
  mounted(){
    fetch("https://api.spacexdata.com/v3/ships")
    .then(result => result.json())
    .then(ships => this.ships = ships)

    eventBus.$on("list-selected", list => {this.selectedList = list})
    eventBus.$on("ship-selected", ship => {this.selectedShip = ship})
  },
  computed:{

  },
  components: {
    "ship-list": ShipList,
    "ship-detail": ShipDetail,
    "single-ship": SingleShip,
    "select-list": SelectList
  },
  methods:{
  }
}
</script>

<style lang="css" scoped>
</style>
