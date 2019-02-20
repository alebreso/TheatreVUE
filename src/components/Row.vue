<template>
  <div class="row">
    <hr>
    <!-- v-for in row and render Seat component -->
    <div class="row-name">Row {{row.row}}</div>
    <app-seat
      v-for="({seat},i) in row.seats"
      :currentSeat="seat"
      :groups="groups"
      :row="row"
      :key="i"
      :class="{orange:attachOrange, red:attachRed}"
    ></app-seat>
  </div>
</template>

<script>
import SeatVue from "./Seat.vue";
export default {
  props: ["row", "groups"],
  data: function() {
    return {
      attachOrange: false,
      attachRed: false
    };
  },
  components: {
    appSeat: SeatVue
  },
  methods: {}
};
</script>

<style>
.row-name {
  display: block;
  position: relative;
  text-align: center;
  border: 1px dashed black;
  width: 100%;
}

.group1 {
  background-color: red;
}

.group2 {
  background-color: orange;
}
</style>
