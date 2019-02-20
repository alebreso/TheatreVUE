<template>
  <div class="legenda container">
    <div class="group1 seat"></div>
    <div>Reserved for Group
      <br>
      {{groups[0].id}}
    </div>
    <br>
    <div class="group2 seat"></div>
    <div>Reserved for Group
      <br>
      {{groups[1].id}}
    </div>
    <br>
    <div class="available seat"></div>
    <div>Seat Available</div>
  </div>
</template>

<script>
export default {
  props: ["groups"]
};
</script>

<style scoped>
div {
  display: inline-block;
}

.legenda {
  position: absolute;
  border: 1px solid black;
  border-radius: 15px;
  background-color: #dcdcdc;
  padding: 10px;
  top: 5px;
  left: 5px;
  width: 25%;
}

.seat {
  width: 30px;
  height: 30px;
}
</style>
