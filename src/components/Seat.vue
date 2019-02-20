<template>
  <div class="text-center seat" :class="divClasses">
    <h4>{{currentSeat}}</h4>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      attachOrange: false,
      attachRed: false
    };
  },
  props: ["currentSeat", "row", "groups"],
  methods: {},
  computed: {
    divClasses: function() {
      return {
        red: this.attachRed,
        orange: this.attachOrange
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
            return;
          } else if (group.id === "+31622222222") {
            this.attachOrange = false;
            this.attachRed = true;
            return;
          } else {
            this.attachOrange = false;
            this.attachRed = false;
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
  font-size: 15px;
  font-weight: bold;
}
h4 {
  margin-top: 25%;
}
</style>
