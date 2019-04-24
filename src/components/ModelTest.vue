<template>
  <div>
    <h1>Model Test</h1>
    <p>{{ checked ? "ON" : "OFF" }}</p>
    <p>
      <button v-on:click="changed">toggle</button>
    </p>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Model, Prop } from "vue-property-decorator";

@Component
export default class ModelTest extends Vue {
  @Prop()
  @Model("change")
  private checked!: boolean;

  changed(event: Event) {
    this.$emit("change", !this.checked);
  }
}
</script>

