<template>
  <div>
    <!-- v-for in row and render Seat component -->
    <div class="left">row {{row.row}}</div>
    <app-seat
      v-for="({seat},i) in row.seats"
      :currentSeat="seat"
      :groups="groups"
      :row="row"
      :key="i"
      :class="{orange:attachOrange, red:attachRed}"
    ></app-seat>
    <hr>
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
  methods: {
  }
};
</script>
<style>
.left {
  position: absolute;
  left: 3px;
}

.orange {
  background-color: orange;
}
.red {
  background-color: red;
}
</style>
