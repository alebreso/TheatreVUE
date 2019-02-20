<template>
  <div 
    class="text-center seat" 
    :class="divClasses" 
  >
    <h4>{{currentSeat}}</h4>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      attachOrange: false,
      attachRed: false,
      isTaken: true,
    };
  },
  props: ["currentSeat", "row", "groups"],
  methods: {},
  computed: {
    divClasses: function() {
      return {
        group1: this.attachRed,
        group2: this.attachOrange,
        available: this.isTaken,
      };
    }
  },
  created() {
    const currentSeat = this.currentSeat;
    this.groups.forEach(group => {
      group.seats.forEach(seat => {
        if (
          parseInt(this.row.row) === parseInt(seat.row) &&
          parseInt(seat.seat) === parseInt(currentSeat)
        ) {
          if (group.id === "+31611111111") {
            this.attachOrange = true;
            this.attachRed = false;
            // this.isTaken = true
            return;
          } else if (group.id === "+31622222222") {
            this.attachOrange = false;
            this.attachRed = true;
            // this.isTaken = true
            return;
          } else {
            this.attachOrange = false;
            this.attachRed = false;
            // this.isTaken = false
            return;
          }
        }
      });
    });
    return;
  }
};
</script>

<style>
.seat {
  display: inline-block;
  border: 1px solid black;
  width: 50px;
  height: 50px;
  background-image: url("../../public/images/theatre_seat-512.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  color: white;
}
h4 {
  margin-top: 25%;
}
.available {

}
</style>
