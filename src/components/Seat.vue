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
  methods: {
  },
  created() {
    const currentSeat = this.currentSeat
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
                this.attachOrange = true
                this.attachRed = false
                return 
              }
              else {
                this.attachOrange = false
                this.attachRed = true
                return 
              }
            }
          }
        });
      });
      // this.attachRed=false
      // this.attachOrange=false
      return
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
