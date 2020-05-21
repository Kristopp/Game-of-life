<template>
  <div class="grid" style="worldCss">
    <FirstCell></FirstCell>
  </div>
</template>
<style src="@/desgin/world.css" lang="css"></style>
<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import FirstCell from "@/components/Cell.vue";
@Component({
  components: {
    FirstCell
  }
})
export default class World extends Vue {
  gridValues = {
    colums: 0,
    rows: 0
  };
  private createGrid(): void {
    console.log();
  }
  mounted() {
    this.createGrid();
  }
}
</script>