<template>
  <div id="app">
    <app-main-hall 
      :section="name" 
      :rows="rows" 
      :groups="groups"></app-main-hall>
    <app-legenda :groups='groups'></app-legenda>
  </div>
</template>

<script>
import MainHallVue from "./components/MainHall.vue";
import LegendaVue from './components/Legenda.vue';
export default {
  name: "app",
  data() {
    return {
      ranks: ["rank1", "rank2", "rank3"],
      name: "main hall",
      rows: [
        {
          row: 1,
          seats: [
            { seat: "1", rank: "rank1" },
            { seat: "3", rank: "rank1" },
            { seat: "4", rank: "rank1" },
            { seat: "2", rank: "rank1" }
          ]
        },
        {
          row: 2,
          seats: [
            { seat: "1", rank: "rank1" },
            { seat: "3", rank: "rank1" },
            { seat: "5", rank: "rank1" },
            { seat: "6", rank: "rank1" },
            { seat: "4", rank: "rank1" },
            { seat: "2", rank: "rank1" }
          ]
        },
        {
          row: 3,
          seats: [
            { seat: "1", rank: "rank2" },
            { seat: "3", rank: "rank2" },
            { seat: "5", rank: "rank2" },
            { seat: "6", rank: "rank2" },
            { seat: "4", rank: "rank2" },
            { seat: "2", rank: "rank2" }
          ]
        }
      ],
      groups: [
        {
          id: "+31611111111",
          seats: [
            { section: "main hall", row: "1", seat: "4" },
            { section: "main hall", row: "1", seat: "2" },
            { section: "main hall", row: "2", seat: "2" },
            { section: "main hall", row: "2", seat: "4" }
          ]
        },
        {
          id: "+31622222222",
          seats: [
            { section: "main hall", row: "2", seat: "6" },
            { section: "main hall", row: "2", seat: "5" }
          ]
        }
      ]
    };
  },
  components: {
    appMainHall: MainHallVue,
    appLegenda: LegendaVue,
  }
};
</script>

<style>
</style>
