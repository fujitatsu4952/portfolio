<template>
  <div class="container">
    <div>
      <h1>fdafad</h1>
      <input v-model="localValue" />
    </div>
  </div>
</template>

<script lang="ts">
// import Vue from "vue";
import { Component, Vue, Prop, Emit } from "nuxt-property-decorator";

@Component({
  components: {}
})
export default class AtomStart extends Vue {
  @Prop() public value!: string;
  @Emit("input")
  public input(value: string) {}

  private get localValue(): string {
    return this.value;
  }

  private set localValue(value: string) {
    this.input(value);
  }
}
</script>

<style></style>
