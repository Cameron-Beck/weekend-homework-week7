<template lang="html">
  <div class="container1">
      <h1>All Ships</h1>
  <ship-list class="ship-list"  :ships = "ships">  </ship-list>

  <ship-detail class="container2" :ship = "selectedShip"> </ship-detail>
  </div>
</template>

<script>
import ShipDetail from "./components/ShipDetail.vue"
import ShipList from "./components/ShipList.vue"
import SingleShip from "./components/SingleShip.vue"

import {eventBus} from "./main.js"
export default {
  name: "App",
  data(){
    return {
      ships: [],
      selectedShip: null,
      favorites: [],
      beerToRemove: ""
    }
  },
  mounted(){
    fetch("https://api.spacexdata.com/v3/ships")
    .then(result => result.json())
    .then(ships => this.ships = ships)

    eventBus.$on("ship-selected", ship => {this.selectedShip = ship})
  },
  computed:{

  },
  components: {
    "ship-list": ShipList,
    "ship-detail": ShipDetail,
    "single-ship": SingleShip
  },
  methods:{
  }
}
</script>

<style lang="css" scoped>
</style>
