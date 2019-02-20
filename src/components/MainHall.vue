<template>
  <div class="container hall text-center">
    <h3>{{sectionToUpperCase()}}</h3>
    <!-- v-for in rows and render a row component -->
    <app-Row 
      v-for="(row, i) in rows" 
      :row="row" 
      :groups="groups" 
      :key="i"></app-Row>
  </div>
</template>

<script>
import RowVue from "./Row.vue";
export default {
  props: ["section", "rows", "groups"],
  data: function() {
    return {};
  },
  components: {
    appRow: RowVue
  },
  methods: {
    sectionToUpperCase() {
      return this.section.toUpperCase();
    }
  }
};
</script>

<style scoped>
.hall {
  margin-top: 30px;
  width: 80%;
  border: 1px solid black;
  position: relative;
  background-color: #dcdcdc;
  padding-bottom: 25px;
  border-radius: 20px
}
</style>
