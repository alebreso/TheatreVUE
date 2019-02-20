<template>
  <div>
    <!-- v-for in row and render Seat component -->
    <span class="left">row {{row.row}}</span>
    <app-seat
      v-for="({seat},i) in row.seats"
      :seat="seat"
      :groups="groups"
      :row="row"
      :key="i"
      :class="isSeatTaken(seat)"
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
      color: ""
    };
  },
  components: {
    appSeat: SeatVue
  },
  methods: {
    isSeatTaken(currentSeat) {
      this.groups.forEach(group => {
        group.seats.forEach(seat => {
          console.log("row.row === seat.row");
          console.log(`${parseInt(this.row.row)} === ${parseInt(seat.row)}`);
          if (parseInt(this.row.row) === parseInt(seat.row)) {
            console.log('inside I if')
            console.log("seat.seat === currentSeat");
            console.log(`${seat.seat} === ${currentSeat}`);
            if (parseInt(seat.seat) === parseInt(currentSeat)) {
              console.log('inside II if')
              console.log("seat.seat === currentSeat");
              console.log(`${group.id} === +31611111111`);
              if (group.id === "+31611111111") {
                console.log('inside III if')
                return { orange: true };
              }
              else return { red: true };
            }
          }
        });
      });
      return { orange: false, red:false};
    }
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
