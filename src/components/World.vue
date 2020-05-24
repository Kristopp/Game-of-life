<template>
  <!-- main container where the magic begins -->
  <div class="grid-container" id="grid-container-id">
    <LivingCell v-if="cellState"></LivingCell>
    <button v-on:click="renderLivingCell" style="margin: 1rem">click</button>
  </div>
</template>
<style src="@/desgin/world.css" lang="css"></style>
<style src="@/desgin/gridCell.css" lang="css"></style>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import LivingCell from "@/components/Cell.vue";
@Component({
  components: {
    LivingCell
  }
})
export default class World extends Vue {
  public cellState = false;
  _i = 0;
  
  /* function to create dynamic grid cells */
  /**loop for dynamic grid */
  createGrid() {
    for (let _i= this.i;_i < 10; this._i++) {
      const getGridCell = `<div class="main-grid" id=${this._i} v-for="item in this.gridId" v-bind:key="item.id">`;
      const element: any = document.querySelector(".grid-container").insertAdjacentHTML('beforeend', getGridCell);
      console.log(element);
    }
  }
  renderLivingCell() {
    this.cellState = true;
  }
  mounted() {
    this.createGrid();
  }
}
</script>