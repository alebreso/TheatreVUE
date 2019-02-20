<template>
  <div class="text-center seat" :class="{red:attachRed,orange:attachOrange}">{{currentSeat}}</div>
</template>
<script>
export default {
  data: function() {
    return {
      attachOrange: true,
      attachRed: false
    };
  },
  props: ["currentSeat", "row", "groups"],
  methods: {},
  created() {
    const currentSeat = this.currentSeat;
    this.attachRed = false;
    this.attachOrange = false;
    this.groups.forEach(group => {
      group.seats.forEach(seat => {
        if (parseInt(this.row.row) === parseInt(seat.row)) {
          if (parseInt(seat.seat) === parseInt(currentSeat)) {
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
        }
      });
    });
    return;
  }
};
</script>
<style scoped>
div {
  display: inline-block;
  border: 1px solid black;
  width: 50px;
  height: 50px;
}
</style>
