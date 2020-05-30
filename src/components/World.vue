+<template>
  <!-- main container where the magic begins -->
  <div class="grid-container" id="grid-container-id">
    <!--Use vue loop to create dynamic grid -->
    <div
      class="main-grid"
      :class="isAlive"
      v-for="(item, index) in gridElements"
      :id="'gridCell' + '-' + [index]"
      :key="item.id"
    >
      <!--  kui parent id  on vordne -->
      <div 
        class="livingCell" 
        v-if="item === gridElements[23]" 
        :style="[cellStyle]">
      </div>
    </div>
    <button style="margin: 1rem">click</button>
  </div>
</template>
<style src="@/desgin/world.css" lang="css"></style>
<style src="@/desgin/gridCell.css" lang="css"></style>
<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Cell from "@/components/Cell.vue";
@Component({
  components: {
    livingcell: Cell
  }
})
export default class World extends Vue {
  gridElements: any = [];
  getId = "";
  isAlive = true;
  cellStyle: object = {
    margin: "auto",
    width: "90%",
    height: "90%",
    backgroundColor: "black"
  };

  public createGridRow() {
    for (let _i = 0; _i < 50; _i++) {
      this.gridElements.push("grid-cell-id" + "-" + `${_i}`);
    }
  }
  mounted() {
    this.createGridRow();
  }
}
</script>