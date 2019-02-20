<template>
  <div class="text-center seat">{{seat}}</div>
</template>
<script>
export default {
  data: function() {
    return {
    };
  },
  props: ["seat", "row", "groups"],
  methods: {
  },
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
