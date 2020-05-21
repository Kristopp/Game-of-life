<template>
  <div id="app">
    <main>
      <World></World>
    </main>
  </div>
</template>
<script lang="ts">
import World from "@/components/World.vue";
import Component from "vue-class-component";
import { Vue } from "vue-property-decorator";

@Component({
  components: { World }
})
export default class App extends Vue {}
</script>
